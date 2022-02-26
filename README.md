# storefront-query-builder

---------

# #TechForUkraine

<table>
  <tr>
    <td style="width:40%;">
       <img src="https://user-images.githubusercontent.com/1626923/155853691-d6d0a541-d3b9-40bf-b8f5-2d38303e9e49.png" />
    </td>
    <td>
      <h2><strong>Ongoing tensions on Ukrainian territory close the space for civil society.</strong></h2>
      <h3>How can you support Ukrainian civil society?</h3>
      All the help is valid, and if you are not able to help locally, by giving shelter to a fellow Ukraine, there are some ways that you can help also:
      <ul>
        <li>
          Support the Ukraine Armed forces directly by sending funding to the open special accounts.<br />
          <a href="https://bank.gov.ua/en/news/all/natsionalniy-bank-vidkriv-spetsrahunok-dlya-zboru-koshtiv-na-potrebi-armiyi" target="_blank">NBU Opens Special Account to Raise Funds for Ukraine’s Armed Forces</a>
        </li>
        <li>
          Help the ICRC (Red Cross) with donations.<br />
          <a href="https://www.icrc.org/en/where-we-work/europe-central-asia/ukraine" target="_blank">Ukrainian Red Cross Society</a>
        </li>
        <li>
          Donate to the United Help Ukraine.<br />
          <a href="https://unitedhelpukraine.org/" target="_blank">United Help Ukraine</a>
        </li>
        <li>
          Donate to Voices of Children<br />
          <a href="https://voices.org.ua/en/" target="_blank">Voices of Children</a>
        </li>
    </td>
  </tr>
</table>

---------

ElasticSearch Query builder from the abstract "SearchQuery" object used by `storefront-api`, `vue-storefront-api` and `vue-storefront` projects.

The idea is, that the user can create the query in a pretty abstract way and get the `ElasticSearch` or potentially different query in return. Some nice extension ideas could be to add `mongodb` support or `SQL` support as well.


Example usage:

```js
import { SearchQuery, elasticsearch } from 'storefront-query-builder'
import bodybuilder from 'bodybuilder'
const searchQuery = new SearchQuery()
searchQuery = searchQuery.applyFilter({key: 'parent_id', value: {'eq': 125 }})
const elasticSearchQuery = await elasticsearch.buildQueryBodyFromSearchQuery({ config, queryChain: bodybuilder(), searchQuery })
// send the `elasticSearchQuery` to ElasticSearch instance
```

More on [`storefront-api`](https://github.com/DivanteLtd/storefront-api)
More on [`vue-storefront`](https://github.com/DivanteLtd/vue-storefront)
