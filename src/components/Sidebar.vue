<template>
    <aside class="  flex 
                    flex-col 
                    bg-[var(--dark)] 
                    text-[color:var(--light)]     
                    min-h-screen
                    p-[1rem]   
                    fixed
                    md:static
                    z-[99] 
                    overflow-hidden"
                :class="`${isExpanded && ' expanded '}`"
                    >
        <div class="logo mb-1">
            <img src="../assets/vue.svg" class="w-[2rem]" alt="logo vue">
        </div>

        <menu class="menu-toggle-wrapper flex justify-end mb-[1rem] relative ">
            <button class="menu-toggle" @click="ToggleMenu">
                <span class="material-icons text-[color:var(--light) hover:text-[color:var(--primary)] text-[2rem]">
                    
                        keyboard_double_arrow_right
                        

                </span>
            </button>
          
        </menu>
        <h3>Menu</h3>
        <menu class="m-[0-1rem] child-hover:text-blue-500 child-hover:bg-blue-300/30 ">
            <router-link class="button" to="/">
                <span class="material-icons">home</span>
                <span class="text" >Home</span>
            </router-link>
            <router-link class="button" to="/about">
                <span class="material-icons">visibility</span>
                <span  class="text">About</span>
            </router-link>
            <router-link class="button" to="/2">
                <span class="material-icons">group</span>
                <span  class="text">Team</span>
            </router-link>
            <router-link class="button" to="/1">
                <span class="material-icons">email</span>
                <span  class="text">Contacts</span>
            </router-link>
        
        </menu>

    </aside>
</template>
<script setup  lang="ts">
import {ref} from "vue"
const isExpanded = ref(false);

const ToggleMenu = ()=>{ isExpanded.value= !isExpanded.value}
</script>


<style lang="scss" scoped>
    h3, .text {
        opacity: 0;
        transition: 0.2s ease-out;
        visibility:hidden;
    }

    .text {
        margin-left: 1rem;
    }

    menu{
        .button{
            display: flex;
            text-decoration: none;
            padding: 0.5rem 1rem;
            align-items: center;
            transition: 0.2 ease-out;
            .material-icons{
                font-size: 2rem;
                color: var(--light);
                transition: 0.2 ease-out;

            }
        }
    }

    .button {
        transition: 0.1s ease-out;

        &.router-link-active{
            border-right: 5px solid white;
        }
    }
    aside{
        transition: 0.2s ease-out;
        width: calc(2rem + 32px);
        .menu-toggle-wrapper{
            top:0px;
            transition: 0.2s ease-out;
        }
        .menu-toggle{
            transition: 0.2s ease-in;

            .material-icons{
                transition: 0.1s ease-in;
                &:hover{
                    transform: translateX(5px);
                }
            }
        }
        &.expanded{
            h3, .text {
                opacity: 1;
                visibility:visible;

        
            }


            width: var(--sidebar-width);
            .menu-toggle-wrapper{
                top: -3rem;
            }
            .menu-toggle{
                transform: rotate(-180deg);
                }

        }
    }
  
</style>