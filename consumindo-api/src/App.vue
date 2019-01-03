<template>
  <div id="app">

    <nav>
      <div class="nav-wrapper blue darken-1">
        <div>
          <div class="brand-logo center">FILTRO DE APROVAÇÔES</div>          
        </div>
        <button class="waves-effect btn-small darken-1 right" @click="show=true">Cadastrar nova Aprovação</button>
      </div>
    </nav>

    <div class="container">
      <div class="row">
        <div class="col s3">
          <label>Selecione o Ano</label>
          <select class="browser-default md-raised">
            <option value="1">2018</option>
            <option value="2">2017</option>
            <option value="3">2016</option>
            <option value="4">2015</option>
          </select>
        </div>

        <div class="col s3">
          <label>Selecione o Estado</label>
          <select class="browser-default md-raised">
            <option value="1">2018</option>
            <option value="2">2017</option>
            <option value="3">2016</option>
            <option value="4">2015</option>
          </select>
        </div>

        <div class="col s3">
          <label>Selecione o Concurso</label>
          <select class="browser-default md-raised"
                :value="null"
                :options="aprovacoes"
                required
                v-model="aprovacoes.year">                
          </select>
        </div>

        <div class="col s3">
          <label>Sigla</label>
          <select class="browser-default md-raised">
            <option value="1">2018</option>
            <option value="2">2017</option>
            <option value="3">2016</option>
            <option value="4">2015</option>
          </select>      
        </div>
      </div>

        <div class="row">
          <div class="col s12">UFRJ - 2018 <br> Universidade Federal do Rio de Janeiro <br> Residência Médica</div>          
        </div>
        <div class="row">          
          <div class="col s12"><h3>RESULTADO FINAL</h3><br>APROVADO EM NEGRITO</div>          
        </div>
        <div class="row">          
          <div class="col s12">HOSPITAL UNIVERSITÁRIO CLEMENTE FRAGA FILHO</div>          
        </div>
        <div class="row">          
          <div class="col s12">ANESTISIOLOGIA</div>          
        </div>
        <div class="row">          
          <div class="col s12">TODOS OS APROVADOS FORAM DO MEDGRUPO!!</div>
        </div>    

      <table>

        <tbody>
            <tr>

            <td>1</td>
            <td>Élenfe Gomes da silva</td>
            <td>MEDGRUPO</td>
            <td>
              <button class="waves-effect btn-small blue darken-1"><i class="material-icons">create</i></button>
              <button class="waves-effect btn-small red darken-1"><i class="material-icons">delete_sweep</i></button>
            </td>

          </tr>

        </tbody>
      
      </table>

    </div>

  </div>

  
</template>

<script>

  import Aprovacoes from './services/aprovacoes'

  export default {

    data(){
      return {
        aprovacoes: [],
        show: false
      }
      
    },

    mounted(){
      Aprovacoes.listar().then(resposta => {
        console.log(resposta.data)
        this.Aprovacoes = resposta.data
      })
    }
  }
</script>
 
<style>

</style>
