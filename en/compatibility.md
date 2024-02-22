---
layout: page              
title: Bitcoin Feature Tracker
permalink: /en/compatibility/
nowrap: true
---

{% assign yes = '<span class="feature-yes"><strong>✓</strong></span>' %}
{% assign no = '<span class="feature-no"><strong>✕</strong></span>' %}

<style>
th, td { text-align: center;}

td.two {
      line-height: 0.90;
    }

h1, h2, h3, h4, h6 { text-align: center; }
h5 { text-align: left; }
</style>

{: .center}



<table class="compatibility">

<tr style="background-color: transparent;">
<td colspan="15" style="text-align:left;font-size:14px;border-top-style: hidden;border-left-style: hidden;border-right-style: hidden;" >
    &#x2705; - Full Support (send & receive)<br/>
    &#x1F4B8; - Send Support<br/>
    &#x274C; - No Support <br/>
    &#x2796; - Not Applicable<br/>
</td>
</tr>
  <tr>
    <th rowspan="2">Product <br/>/ <br/>Service </th>
    <th rowspan="2">Category</th>
    <th rowspan="2" width="265px">Key Features / <br/>Use Cases</th>
    <th colspan="4" style="color:blue;">Native Segwit</th>
    <th colspan="2" style="color:blue;">Fee Bumping </th>
    <th colspan="4" style="color:blue;">Multi-Party Transactions </th>
    <th rowspan="2"><a href="https://bitcoinops.org/en/topics/silent-payments/">Silent <br/>Payments </a></th>
    <th rowspan="2">Lightning</th>
  </tr>
  <tr>
    <th style="vertical-align:top;"><a href="https://bitcoinops.org/en/topics/bech32/">Bech32 <br/><font color="grey">P2WPKH<br/>P2WSH</font></a> </th>
    <th style="vertical-align:top;"><a href="https://bitcoinops.org/en/topics/bech32/">Bech32m <br/><font color="grey">P2TR</font></a></th>
    <th>Default <br/>Receive<br/> Address</th>
    <th>Native <br/>Segwit<br/> Change</th>  
    <th><a href="https://bitcoinops.org/en/topics/replace-by-fee/">RBF</a></th>  
    <th><a href="https://bitcoinops.org/en/topics/cpfp/">CPFP</a></th>  
    <th><a href="https://bitcoinops.org/en/topics/psbt/">PSBT</a></th>   
    <th><a href="https://bitcoinops.org/en/topics/musig/">MuSig2</a></th>   
    <th><a href="https://bitcoinops.org/en/topics/payjoin/">Payjoin</a></th>   
    <th><a href="https://bitcoinops.org/en/topics/coinjoin/">Coinjoin</a></th>     
  </tr>
  {% assign tools = site.data.compatibility | sort %}    

  {% for wrapped_tool in tools %}   
    {% assign tool = wrapped_tool[1] %}
      {% if tool.feature %}
        <tr>
          <td><a href="{{tool.homepage}}">{{tool.name}}</a></td>
          <td>{{tool.category}}</td>
          <td class="two"><font size="2">{{tool.keyfeatures}}</font></td>

          {% include functions/compat-cell-1-input.md state=tool.feature.bech32 %}

          {% include functions/compat-cell-1-input.md state=tool.feature.bech32m %}

          <td>{{tool.feature.segwit_default_receive}}</td>

          {% include functions/compat-cell-1-input.md state=tool.feature.segwit_change %}

          {% include functions/compat-cell-1-input.md state=tool.feature.rbf %}


          {% include functions/compat-cell-1-input.md state=tool.feature.cpfp %}


          {% include functions/compat-cell-1-input.md state=tool.feature.pbst %}


          {% include functions/compat-cell-1-input.md state=tool.feature.musig2 %}


          {% include functions/compat-cell-1-input.md state=tool.feature.payjoin %}


          {% include functions/compat-cell-1-input.md state=tool.feature.coinjoin %}


          {% include functions/compat-cell-1-input.md state=tool.feature.silent_payments %}


          {% include functions/compat-cell-1-input.md state=tool.feature.lightning %}

        </tr>
      {% endif %}

  {% endfor %}

  <tr style="background-color: transparent;">
  <td colspan="15" style="text-align:left;font-size:14px;border-bottom-style: hidden;border-left-style: hidden;border-right-style: hidden;" >
  <span class="bold">Notes:</span><br/>   
  &#x1F538; To qualify as having Bech32 sending support, a product should be able to send to both P2WPKH and P2WSH<br/>
  &#x1F538; To qualify as having Bech32 receiving support, it is sufficient to receive to either P2WPKH or P2WSH<br/>
  &#x1F538; Lightning only “Pay Invoice” and “Create Invoice” capabilities are considered.<br/>
  </td>

  </tr>
  <tr style="background-color: transparent;">
  <td colspan="15" style="text-align:left;font-size:14px;border-bottom-style: hidden;border-left-style: hidden;border-right-style: hidden;" >
  <span class="bold">Approach:</span><br/>   
  &#x1F538; The initial features within the tracker have been selected by bitcoinops with a focus on scaling and privacy.  <br/>
  &#x1F538; New feature as well as product/service requests are welcome here:  info@bitcoinops.org<br/>
  </td>
  </tr>

  </table>

<br/>
<br/>
_Contributions and corrections are welcome. Please see the [contibuting
guidelines](https://github.com/bitcoinops/bitcoinops.github.io/blob/master/CONTRIBUTING.md)
for details._
{: style="text-align: center;"}
