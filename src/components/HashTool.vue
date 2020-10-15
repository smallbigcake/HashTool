<template>
    <div class="hash" :style="{textAlign: ['center', '-webkit-center']}">
        <h1>{{ msg }}</h1>
        <p>
            Input text below to show hash:
        </p>
        <label>
            <textarea type="text" v-model="text"></textarea>
        </label>
        <h3>Hash</h3>
        <div>
            <table>
                <tr
                    v-for="hash_type in hash_list"
                    :key="hash_type.name"
                >
                    <td>{{ hash_type.name }}</td>
                    <td>{{ this[hash_type.key] }}</td>
                </tr>
            </table>
        </div>

    </div>
</template>

<script>

import md5 from "crypto-js/md5"
import sha1 from "crypto-js/sha1";
import sha256 from "crypto-js/sha256";
import sha384 from "crypto-js/sha384";
import sha512 from "crypto-js/sha512";

export default {
    name: 'HashTool',
    props: {
        msg: String``
    },
    data () {
        return {
            text: "",
            hash_list: {
                md5: {
                    name: "MD5",
                    key: "md5"
                },
                sha1: {
                    name: "SHA1",
                    key: "sha1"
                },
                sha256: {
                    name: "SHA256",
                    key: "sha256"
                },
                sha384: {
                    name: "SHA384",
                    key: "sha384"
                },
                sha512: {
                    name: "SHA512",
                    key: "sha512"
                }
            }
        }
    },
    computed: {
        md5() {
            return md5(this.text).toString();
        },
        sha1() {
            return sha1(this.text).toString();
        },
        sha256() {
            return sha256(this.text).toString();
        },
        sha384() {
            return sha384(this.text).toString();
        },
        sha512() {
            return sha512(this.text).toString();
        }
    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
    margin: 40px 0 0;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}

textarea {
    width: 600px;
    height: 200px;
}

table {
    border-width: 1px;
    border-style: solid;
    border-collapse: collapse;
}

td {
    padding: 10px;
    border-style: solid;
    border-width: 1px;
}

</style>
