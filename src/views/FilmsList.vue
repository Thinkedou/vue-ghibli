<template>
    <table class="styled-table">
      <thead>
          <tr>
              <th>Id</th>
              <th>Name</th>
              <th>Year</th>
              <th>Voir</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td>2</td>
              <td>Truc</td>
              <td>2019</td>
              <td>👀</td>
          </tr>
          <tr>
              <td>3</td>
              <td>Chateau</td>
              <td>2019</td>
              <td>👀</td>
          </tr>
          <!-- and so on... -->
      </tbody>
  </table>
</template>

<script>


export default {
  name: 'FilmsList',
  components: {
    }
}
</script>
<style scoped>
.styled-table {
    border-collapse: collapse;
    margin: 25px 0;
    font-size: 0.9em;
    font-family: sans-serif;
    min-width: 800px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}
.styled-table thead tr {
    background-color: #009879;
    color: #ffffff;

}
.styled-table th,
.styled-table td {
    padding: 12px 15px;
}
.styled-table tbody tr {
    border-bottom: 1px solid #dddddd;
}

.styled-table tbody tr:nth-of-type(even) {
    background-color: #f3f3f3;
}

.styled-table tbody tr:last-of-type {
    border-bottom: 2px solid #009879;
}

.styled-table tbody tr.active-row {
    font-weight: bold;
    color: #009879;
}




</style>
