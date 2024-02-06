---
layout: post
title: Database Get
hide: true
description:
permalink: /data/database
---

## Database of Users

<table>
  <thead>
  <tr>
    <th>Name</th>
    <th>ID</th>
    <th>Email</th>
    <th>Role</th>
  </tr>
  </thead>
  <tbody id="result">
  </tbody>
</table>

<script type="module">
  import { uri, options } from '{{site.baseurl}}/assets/js/api/config.js';

  const url = uri + '/api/users/';

  const resultContainer = document.getElementById("result");

  fetch(url, options)
    .then(response => {
      if (response.status === 401) {
        window.location.href = '{{site.baseurl}}/login';
        return;
      }
      if (response.status === 403){
        window.location.href = '{{site.baseurl}}/403';
        return;
      }

      if (response.status !== 200) {
        const errorMsg = 'Database response error: ' + response.status;
        console.log(errorMsg);
        const tr = document.createElement("tr");
        const td = document.createElement("td");
        td.innerHTML = errorMsg;
        tr.appendChild(td);
        resultContainer.appendChild(tr);
        return;
      }

      response.json().then(data => {
        console.log(data);
        for (const row of data) {
          const tr = document.createElement("tr");
          const name = document.createElement("td");
          const id = document.createElement("td");
          const email = document.createElement("td");
          const role = document.createElement("td");

          name.innerHTML = row.name; 
          id.innerHTML = row.uid; 
          email.innerHTML = row.email; 
          role.innerHTML = row.role

          tr.appendChild(name);
          tr.appendChild(id);
          tr.appendChild(email);
          tr.appendChild(role);
          resultContainer.appendChild(tr);
        }
      });
    })
    .catch(err => {
      console.error(err);
      const tr = document.createElement("tr");
      const td = document.createElement("td");
      td.innerHTML = err + ": " + url;
      tr.appendChild(td);
      resultContainer.appendChild(tr);
    });
</script>
