<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Remote
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
We are moving out offices and spending more time working in our homes, leading to more meals in, more home improvement, and more time spent on entertainment.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| AAPL | Apple sees increased sales in Macs, iPads, and services as remote work and entertainment needs grow. | chat_gpt |
| ADBE | Adobe benefits from increased use of its creative and document management software by remote workers. | chat_gpt |
| AMZN | Amazon benefits from a surge in online shopping for home essentials and entertainment options. | chat_gpt,claude,twitter,google |
| COST | Costco benefits from increased consumer stockpiling of groceries and essentials for longer home stays. | chat_gpt,claude |
| DELL | Dell Technologies benefits from increased demand for personal computers and IT solutions for remote work. | chat_gpt |
| DIS | Disney benefits from increased subscriptions to its Disney+ streaming service as families seek home entertainment. | chat_gpt,claude,google |
| DOCU | DocuSign benefits from the increased adoption of digital document management and e-signature solutions in remote work environments. | chat_gpt,google |
| ETSY | Etsy benefits from increased consumer interest in personalized and home-crafted goods. | chat_gpt |
| HD | Home Depot sees increased sales from home improvement projects as people spend more time at home. | chat_gpt,claude,google |
| LOW | Lowe's benefits similarly to Home Depot, with increased demand for home improvement supplies. | chat_gpt,claude,google |
| MSFT | Microsoft benefits from higher usage of its Office 365 suite and Teams for remote work and collaboration. | chat_gpt,twitter,google |
| NFLX | Netflix gains from higher demand for home entertainment as people spend more time indoors. | chat_gpt,claude,google |
| PTON | Peloton benefits from higher demand for home fitness equipment and subscription services. | chat_gpt,claude |
| ROKU | Roku benefits from increased demand for streaming devices as home entertainment becomes more central. | chat_gpt,claude,google |
| TGT | Target benefits from increased sales in home goods, electronics for entertainment, and groceries. | chat_gpt,claude |
| WMT | Walmart benefits from increased demand for groceries and home goods as more meals are eaten at home. | chat_gpt,claude |
| ZM | Zoom Video Communications benefits directly as remote work increases, driving demand for video conferencing. | chat_gpt,twitter,google |
| CMCSA |  | claude,google |
| KR |  | claude |
| LULU |  | claude |
| NKE |  | claude |
| SYY |  | claude |
| WHR |  | claude |
| AI |  | twitter |
| CRM |  | twitter |
| GOOGL |  | twitter,google |
| META |  | twitter |
| MRNA |  | twitter |
| ARHS |  | google |
| BOX |  | google |
| ESTC |  | google |
| FND |  | google |
| HVT |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/remote/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/remote" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
