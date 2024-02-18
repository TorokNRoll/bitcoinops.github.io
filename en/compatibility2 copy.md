---
layout: page              
title: Bitcoin Best Practice Adoption Tracker
permalink: /en/compatibility2/
nowrap: true
---

{% assign yes = '<span class="feature-yes"><strong>✓</strong></span>' %}
{% assign no = '<span class="feature-no"><strong>✕</strong></span>' %}

<style>
th, td { text-align: center; }
h1, h2, h3, h4, h5, h6 { text-align: center; }
</style>

{: .center}

<table class="compatibility">
  <tr>
    <th rowspan="3">Product / Service </th>
    <th rowspan="3">Category</th>
    <th colspan="5" style="color:blue;">Native Segwit</th>
    <th colspan="2" style="color:blue;">Fee Bumping </th>
    <th colspan="4" style="color:blue;">Multi-Party Transactions </th>
    <th rowspan="3">Silent Payments </th>
    <th rowspan="3">Lightning</th>
  </tr>
  <tr>
    <th colspan="2">Bech32 </th>
    <th>Bech32m</th>
    <th rowspan="2">Default Receive Address</th>
    <th rowspan="2">Native Segwit Change</th>  
    <th rowspan="2">RBF</th>  
    <th rowspan="2">CPFP</th>  
    <th rowspan="2">PBST</th>   
    <th rowspan="2">MuSig2</th>   
    <th rowspan="2">Payjoin</th>   
    <th rowspan="2">Coinjoin</th>     
  </tr>
  <tr>
    <th>P2WPKH</th>
    <th>P2WSH</th>
    <th>P2TR</th>
  </tr>
  {% assign tools = site.data.compatibility | sort %}    

  {% for wrapped_tool in tools %}   
    {% assign tool = wrapped_tool[1] %}
      {% if tool.bestpractice %}
        <tr>
          <td><a href="{{tool.internal_url}}#segwit">{{tool.name}}</a></td>
          <td>{{tool.category}}</td>


          {% include functions/compat-cell.md state=tool.bestpractice.p2wpkh_send state2=tool.bestpractice.p2wpkh_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.p2wsh_send state2=tool.bestpractice.p2wsh_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.p2tr_send state2=tool.bestpractice.p2tr_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.segwit_change %}

          {% include functions/compat-cell.md state=tool.bestpractice.segwit_change %}

          {% include functions/compat-cell.md state=tool.bestpractice.rbf_send state2=tool.bestpractice.rbf_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.cpfp_send state2=tool.bestpractice.cpfp_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.pbst_send state2=tool.bestpractice.pbst_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.musig2_send state2=tool.bestpractice.musig2_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.payjoin_send state2=tool.bestpractice.payjoin_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.coinjoin_send state2=tool.bestpractice.coinjoin_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.silent_payments_send state2=tool.bestpractice.silent_payments_receive %}


          {% include functions/compat-cell.md state=tool.bestpractice.lightning_send state2=tool.bestpractice.lightning_receive %}

        </tr>
      {% endif %}
  {% endfor %}

  </table>

<br/>
<br/>
_Contributions and corrections are welcome. Please see the [contibuting
guidelines](https://github.com/bitcoinops/bitcoinops.github.io/blob/master/CONTRIBUTING.md)
for details._
{: style="text-align: center;"}
