<template>
  <!------------------------------------------------------------------ Main Board Option 2 ------------------------------------------------------------------>
<div class="overflow-x-auto max min-h-screen bg-fixed lg:max-h-screen" id="page-main">
    <nav class="bg-gray-800 sticky top-0 left-0 z-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between h-16">
          <div class="flex items-center">
            <div class="text-2xl font-extrabold select-none">
                <span class="bg-clip-text text-transparent bg-gradient-to-r from-green-400 to-blue-500">
                Kanbund
                </span>
            </div>
            <div class="hidden md:block">
              <div class="ml-10 flex items-baseline space-x-4">
                <!-- <a href="#" class="px-3 py-2 rounded-md text-sm font-medium text-white bg-gray-900">Dashboard</a>
  
                <a href="#" class="px-3 py-2 rounded-md text-sm font-medium text-gray-300 hover:text-white hover:bg-gray-700">Team</a>
  
                <a href="#" class="px-3 py-2 rounded-md text-sm font-medium text-gray-300 hover:text-white hover:bg-gray-700">Projects</a>
  
                <a href="#" class="px-3 py-2 rounded-md text-sm font-medium text-gray-300 hover:text-white hover:bg-gray-700">Calendar</a>
  
                <a href="#" class="px-3 py-2 rounded-md text-sm font-medium text-gray-300 hover:text-white hover:bg-gray-700">Reports</a> -->
              </div>
            </div>
          </div>
          <div class="hidden md:block">
            <div class="ml-4 flex items-center md:ml-6">
              
  
              <!-- Profile dropdown -->
              <div class="ml-3 relative">
                <div>
                  <button @click="toggleOptionUser = true" 
                  class="max-w-xs  py-1 px-3 text-white bg-gray-800 rounded-md flex items-center  font-bold focus:outline-none focus:ring-2 focus:ring-offset-2  focus:ring-gray-900 focus:bg-gray-900" id="user-menu" aria-haspopup="true">
                    <span class="sr-only text-white">Open user menu</span>
                    {{activeUser.username}}
                  </button>
                </div>
                <!--
                  Profile dropdown panel, show/hide based on dropdown state.
  
                  Entering: "transition ease-out duration-100"
                    From: "transform opacity-0 scale-95"
                    To: "transform opacity-100 scale-100"
                  Leaving: "transition ease-in duration-75"
                    From: "transform opacity-100 scale-100"
                    To: "transform opacity-0 scale-95"
                -->
                <div v-if="toggleOptionUser" v-on-clickaway="away" 
                class="origin-top-right absolute right-0 mt-2 w-48 rounded-md shadow-lg py-1 bg-white ring-1 ring-black ring-opacity-5" role="menu" aria-orientation="vertical" aria-labelledby="user-menu">
                  <!-- <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100" role="menuitem">Your Profile</a> -->
  
                  <a href="#" @click.prevent="logout" @blur="toggleOptionUser = false" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100" role="menuitem">Log out</a>
                </div>
              </div>
            </div>
          </div>
          <div class="-mr-2 flex md:hidden">
            <!-- Mobile menu button -->
            <button class="bg-gray-800 inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white">
              <span class="sr-only">Open main menu</span>
              <!--
                Heroicon name: menu
  
                Menu open: "hidden", Menu closed: "block"
              -->
              <svg class="block h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
              </svg>
              <!--
                Heroicon name: x
  
                Menu open: "block", Menu closed: "hidden"
              -->
              <svg class="hidden h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>
          </div>
        </div>
      </div>
  
      <!--
        Mobile menu, toggle classes based on menu state.
  
        Open: "block", closed: "hidden"
      -->
      <div class="hidden md:hidden">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-white bg-gray-900">Dashboard</a>
  
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:text-white hover:bg-gray-700">Team</a>
  
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:text-white hover:bg-gray-700">Projects</a>
  
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:text-white hover:bg-gray-700">Calendar</a>
  
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:text-white hover:bg-gray-700">Reports</a>
        </div>
        <div class="pt-4 pb-3 border-t border-gray-700">
          <div class="flex items-center px-5">
            <div class="flex-shrink-0">
              <img class="h-10 w-10 rounded-full" src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="">
            </div>
            <div class="ml-3">
              <div class="text-base font-medium leading-none text-white">Tom Cook</div>
              <div class="text-sm font-medium leading-none text-gray-400">tom@example.com</div>
            </div>
            <button class="ml-auto bg-gray-800 flex-shrink-0 p-1 rounded-full text-gray-400 hover:text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white">
              <span class="sr-only">View notifications</span>
              <!-- Heroicon name: bell -->
              <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
              </svg>
            </button>
          </div>
          <div class="mt-3 px-2 space-y-1">
            <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-400 hover:text-white hover:bg-gray-700">Your Profile</a>
  
            <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-400 hover:text-white hover:bg-gray-700">Settings</a>
  
            <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-400 hover:text-white hover:bg-gray-700">Sign out</a>
          </div>
        </div>
      </div>
    </nav>
  
    <header class="bg-white shadow sticky left-0">
      <div class="max-w-7xl mx-auto py-4 px-4 sm:px-6 lg:px-8">
        <span class="text-xl font-bold leading-tight text-gray-900">
          {{organization.name}}'s Kanban Board
        </span>
        <button class="ml-2 mx-auto bg-gray-900 py-1 px-4 rounded-md text-white font-medium hover:bg-gray-400 hover:text-gray-900" @click="goTo('pg-regOrg')">Change</button>
      </div>
    </header>
    <main class="pt-8">
    <!-- <main style="min-height: 81vh;" class="overflow-x-auto"> -->
        <div class="flex flex-row flex-nowrap gap-x-8 items-start px-8 w-max" id="main-content">
            <board  v-for="cat in categories " 
                    :key="cat.id"
                    :cat="cat"
                    :tasks="cat.Tasks"
                    :optionInfo="checkIndex"
                    @postNewTask="createNewTask"
                    @catDownBoard="catDownHome"
                    @deleteThisBoard="deleteThisHome"
                    @editThisBoard="editThisHome"
                    @catUpBoard="catUpHome"
                    @editBoardName="editBoardName"
                    @updateCat="updateCat"
                    @deleteCat="deleteCat">
            </board>

            <div class="flex-none  mb-4 max-w-xs bg-white shadow overflow-hidden sm:rounded-lg rounded shadow-md hover:shadow-2xl hover:bg-gray-50 lg:mb-0 " >
              <button class="self-center py-2.5 px-4 text-base leading-6 font-semibold bg-gray-900 text-white text-center hover:bg-white hover:text-black"
                      @click="onAddCat = true">
                Add Board
              </button>
            </div>
        </div>
    </main>
    
    <modalEdit v-if="onEdit"
                @cancelEdit="onEdit = false "
                :task="taskOnEdit"
                @postEdit="commitEdit">
    </modalEdit>

    <modalError v-if="errorData"
                :errorData="errorData"
                @closeError="clearError">
    </modalError>
    
    <modalAddCat v-if="onAddCat"
                  @cancelAdd="onAddCat = false"
                  @addCat="addCat">
    </modalAddCat>

</div>
</template>

<script>
import axios from 'axios';
import board from './board'
import modalEdit from './modalEdit'
import modalError from './modalError'
import { directive as onClickaway } from 'vue-clickaway';
import draggable from 'vuedraggable'
import modalAddCat from './modalAddCat'

export default {
    name: 'homepage',
    components: {
        board,
        modalEdit,
        modalError,
        draggable,
        modalAddCat
    },
    props: ['organization', 'categories', 'errorData', 'activeUser'],
    directives: {
    onClickaway: onClickaway,
    },
    data () {
        return {
            onEdit: false,
            taskOnEdit: '',
            onError: false,
            toggleOptionUser: false,
            onAddCat: false
        }
    },
    methods: {
        createNewTask (title, des, catId) {
            console.log(title, des, catId, this.organization.id, 'from homepage')
            this.$emit('createNewTask', title, des, catId, this.organization.id)
        },
        catDownHome (taskId, catId) {
            this.$emit('commitPatch', taskId, catId)
            console.log(taskId, catId, this.organization.id, 'dari homepage catDownHome')
        },
        deleteThisHome (taskId, catId) {
            this.$emit('deleteThisTask', taskId)
            console.log(taskId, catId, this.organization.id, 'dari homepage deleteThisHome')
        },
        editThisHome (task, catId) {
            this.onEdit = true
            this.taskOnEdit = {
                id:task.id,
                title:task.title,
                description:task.description,
                catId: catId
            }
            console.log(task, catId, this.organization.id, 'dari homepage editThisHome')
        },
        catUpHome (taskId, catId) {
            this.$emit('commitPatch', taskId, catId)
            console.log(taskId, catId, this.organization.id, 'dari homepage catUpHome')
        },
        commitEdit (title, des) {
            this.onEdit = false
            const data = {
                id: this.taskOnEdit.id,
                title: title,
                description: des,
                CategoryId: this.taskOnEdit.catId,
                OrganizationId: this.organization.id
            }
            console.log(data)
            this.$emit('commitEdit', data)
        },
        clearError () {
          this.$emit('clearError')
        },
        logout () {
          console.log('logout')
          this.$emit('logout')
        },
        away () {
          this.toggleOptionUser = false
        },
        editBoardName (newName, id) {
          this.$emit('editBoardName', newName, id)
        },
        updateCat(taskId, catId) {
          this.$emit('updateCat', taskId, catId)
        },
        goTo(val) {
          this.$emit('goTo', val)
        },
        addCat(val) {
          this.$emit('addCat', val)
        },
        deleteCat(val) {
          this.$emit('deleteCat', val)
        }
    },
    created: function () {
        this.$emit('getData')
        this.$emit('getUser')
    },
    computed: {
      checkIndex () {
        return {
          li: this.categories[this.categories.length-1].id,
          fi: this.categories[0].id
        }
      }
    }
}
</script>

<style>

</style>