<template>
    <div>
        <test ref="diag"
                v-bind:model-data="diagramData" 
                v-on:model-changed="modelChanged"
                v-on:changed-selection="changedSelection"
        ></test>
    </div>
</template>
<script>
import Test from '@/components/DynamicPorts.vue'
export default {
    components:{
        Test
    },
    data() {
        return {
            diagramData: {  // passed to  as its modelData
            "class": "go.GraphLinksModel",
  "copiesArrays": true,
  "copiesArrayObjects": true,
  "linkFromPortIdProperty": "fromPort",
  "linkToPortIdProperty": "toPort",
  "nodeDataArray": [
{"key":1, "name":"unit One", "loc":"101 204",
 "leftArray":[ {"portColor":"#425e5c", "portId":"left0"} ],
 "topArray":[ {"portColor":"#d488a2", "portId":"top0"} ],
 "bottomArray":[ {"portColor":"#316571", "portId":"bottom0"} ],
 "rightArray":[ {"portColor":"#923951", "portId":"right0"},{"portColor":"#ef3768", "portId":"right1"} ] },
{"key":2, "name":"unit Two", "loc":"320 152",
 "leftArray":[ {"portColor":"#7d4bd6", "portId":"left0"},{"portColor":"#cc585c", "portId":"left1"},{"portColor":"#b1273a", "portId":"left2"} ],
 "topArray":[ {"portColor":"#14abef", "portId":"top0"} ],
 "bottomArray":[ {"portColor":"#dd45c7", "portId":"bottom0"},{"portColor":"#995aa6", "portId":"bottom1"},{"portColor":"#6b95cb", "portId":"bottom2"} ],
 "rightArray":[  ] },
{"key":3, "name":"unit Three", "loc":"384 319",
 "leftArray":[ {"portColor":"#bd8f27", "portId":"left0"},{"portColor":"#c14617", "portId":"left1"},{"portColor":"#47fa60", "portId":"left2"} ],
 "topArray":[ {"portColor":"#d08154", "portId":"top0"} ],
 "bottomArray":[ {"portColor":"#6cafdb", "portId":"bottom0"} ],
 "rightArray":[  ] },
{"key":4, "name":"unit Four", "loc":"138 351",
 "leftArray":[ {"portColor":"#491389", "portId":"left0"} ],
 "topArray":[ {"portColor":"#77ac1e", "portId":"top0"} ],
 "bottomArray":[ {"portColor":"#e9701b", "portId":"bottom0"} ],
 "rightArray":[ {"portColor":"#24d05e", "portId":"right0"},{"portColor":"#cfabaa", "portId":"right1"} ] }
 ],
  "linkDataArray": [
{"from":4, "to":2, "fromPort":"top0", "toPort":"bottom0"},
{"from":4, "to":2, "fromPort":"top0", "toPort":"bottom0"},
{"from":3, "to":2, "fromPort":"top0", "toPort":"bottom1"},
{"from":4, "to":3, "fromPort":"right0", "toPort":"left0"},
{"from":4, "to":3, "fromPort":"right1", "toPort":"left2"},
{"from":1, "to":2, "fromPort":"right0", "toPort":"left1"},
{"from":1, "to":2, "fromPort":"right1", "toPort":"left2"}
 ]
        },
        }
    },
    methods:{
        model: function() { return this.$refs.diag.model(); },
        // tell the GoJS Diagram to update based on the arbitrarily modified model data
        updateDiagramFromData: function() { this.$refs.diag.updateDiagramFromData(); },
        // this event listener is declared on the <diagram>
        modelChanged: function(e) {
            console.log('test')
        //   if (e.isTransactionFinished) {  // show the model data in the page's TextArea
        //     this.savedModelText = e.model.toJson();
        //   }
        },
        changedSelection: function(e) {
            console.log(e)
        //   var node = e.diagram.selection.first();
        //   if (node instanceof go.Node) {
        //     this.currentNode = node;
        //     this.currentNodeText = node.data.text;
        //   } else {
        //     this.currentNode = null;
        //     this.currentNodeText = "";
        //   }
        },

    }
}
</script>
<style scoped>

</style>
