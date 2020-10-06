<p id="notice"><%= notice %></p>


<p><strong>Data:</strong> <%= data_br(Date.today) %> </p>

<h1>Coins</h1>

<table>
  <thead>
    <tr>
      <th><%= @coin.human_atribute_name(:description)%></th>
      <th><%= @coin.human_atribute_name(:acronym)%></th>
      <th><%= @coin.human_atribute_name(:url_image)%></th>
      <th colspan="3"></th>
    </tr>
  

  <tbody>
    <% @coins.each do |coin| %>
  <tr>
        <td><%= coin.description %></td>
        <td><%= coin.acronym %></td>
        <td><%= image_tag coin.url_image, size:  "25x25" %></td>
        <td><%= link_to t( 'links.show'), coin %></td>
        <td><%= link_to t( 'links.edit'), edit_coin_path(coin) %></td>
        <td><%= link_to t( 'links.delete'), coin, method: :delete, data: { confirm: 'Você tem certeza que deseja deletar?' } %></td>
      </tr> </thead>
    <% end %>
  </tbody>
</table>

<br>

<%= link_to 'Nova Moeda', new_coin_path %>

<p>

        <%= link_to 'BACK', welcome_index_path %>
    
<p>
