<v-flex xs12>
    
    <v-list-item
        
        >
        <template v-slot:prepend="{  }">
          <v-col md="8" >
          Completion
          </v-col>
          <v-col md="8">
            Title
          </v-col>
          <v-col md="8">
           Deadline
          </v-col>
          <v-col md="8">
      Delete
          </v-col>
          <v-col md="8">
          Update
      </v-col>
       
           
          </template>
  
        </v-list-item>
         </v-flex> 
        <v-list select-strategy="multiple" class="pt-0" >
  <div v-for="task in tasks" :key="task.id" tasks_prop.sync="tasks">
      
      <v-flex  >
    <v-list-item
        @click="doneTask(task.id)"
        :class="{ 'bg-green ' : task.done}"
        >
        <template v-slot:prepend="{  }">
          <v-col md="10"  >
            <v-list-item-action start>
              <v-checkbox-btn :model-value="task.done"></v-checkbox-btn>
            </v-list-item-action>
          </v-col>
          <v-col md="10">
            <v-list-item-title :class="{ ' text-decoration-line-through' : task.done}"> <text>{{ task.title }}</text></v-list-item-title>
          </v-col>
          <v-col md="10" max-width="200px">
            <v-list-item-title :class="{ ' text-decoration-line-through' : task.done}"> <text>{{ task.Deadline }}</text></v-list-item-title>
          </v-col>
          <v-col md="10">
            <v-list-item-action>
            <v-btn 
            @click.stop="deleteTask(task.id)"
            icon>
              <v-icon color="blue lighten-1">mdi-delete</v-icon>
            </v-btn>
          </v-list-item-action>
      </v-col>
          <v-col md="6">
          <v-list-item-action>
            <EditTask :id=task v-bind:tasks="tasks" v-if="!task.done"></EditTask>
          </v-list-item-action>
      </v-col>
       
           
          </template>
  
        </v-list-item>
         </v-flex> 
        </div>
     
    </v-list>