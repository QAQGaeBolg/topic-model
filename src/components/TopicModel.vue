<template>
    <div class="common-layout">
        <el-container>
            <el-header>
                <Menu/>
            </el-header>
            <el-container>
                <el-container>
                    <el-aside width="200px">
                        <Navigator @selection="changeSelect"/>
                    </el-aside>
                    <el-main >
                        <Subject v-bind:selection="navigate"/>
                    </el-main>                
                </el-container>
                <el-footer>
                    <Authority/>
                </el-footer>
            </el-container>
        </el-container>
    </div>
</template>

<script setup lang = 'ts'>
import { ref } from 'vue'
import Navigator from './elements/Navigator.vue'
import Menu from './elements/Menu.vue'
import Authority from './elements/Authority.vue'
import Subject from './elements/Subject.vue'
const navigate = ref("Upload")
const changeSelect = (selection: string) => {
    navigate.value = selection
}
const windowHeight = () => {
    return (document.documentElement.clientHeight - 210) + 'px'
}
</script>

<style scoped>
.auth-footer {
    display: inline;
}
</style>