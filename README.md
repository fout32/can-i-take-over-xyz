![image](https://user-images.githubusercontent.com/18099289/45263787-a4bbc880-b430-11e8-9cff-eb6e4c796050.png)

## Disclaimer :warning:

**Авторы этого документа не несут никакой ответственности за правильность. Этот проект предназначен лишь для того, чтобы помочь исследователям безопасности определить, является ли что-то уязвимым или нет, но не гарантирует точности. Этот проект в значительной степени зависит от вклада общественности; поэтому доказательство того, что что-то уязвимо, является исключительным правом исследователя безопасности и программы вознаграждения за ошибки. Кроме того, стоит отметить, что некоторые программы поиска ошибок могут принимать отчеты о зависших записях DNS, не требуя доказательств компрометации.**

## Что такое захват поддомена?

> Уязвимости при захвате поддомена возникают, когда поддомен (subdomain.example.com ) указывает на сервис (например, GitHub pages, Heroku и т.д.), который был удален или удалили. Это позволяет злоумышленнику настроить страницу в используемой службе и указать свою страницу на этот поддомен. Например, если subdomain.example.com указывал на страницу GitHub, и пользователь решил удалить свою страницу GitHub, теперь злоумышленник может создать страницу GitHub, добавить файл CNAME, содержащий subdomain.example.com , и заявлять subdomain.example.com .

Подробнее о захвате поддоменов вы можете прочитать здесь:

- <https://labs.detectify.com/2014/10/21/hostile-subdomain-takeover-using-herokugithubdesk-more/>
- <https://www.hackerone.com/blog/Guide-Subdomain-Takeovers>
- <https://0xpatrik.com/subdomain-takeover-ns/>

## Безопасная демонстрация захвата поддомена

Основываясь на личном опыте, незаметного обращения к поддомену и предоставления безопасного файла на скрытой странице обычно достаточно, чтобы продемонстрировать уязвимость в системе безопасности. Не размещайте контент на индексной странице. Хорошим доказательством концепции может служить HTML-комментарий, отправленный по случайному пути:

```
$ cat aelfjj1or81uegj9ea8z31zro.html
<!-- PoC by username -->
```

Пожалуйста, имейте в виду, что это зависит от того, на какую программу вознаграждения за ошибки вы нацелены. Если вы сомневаетесь, пожалуйста, ознакомьтесь с политикой безопасности программы вознаграждения за ошибки и / или запросите разъяснения у команды, стоящей за программой.

## Как использовать этот проект

Я рекомендую поискать название службы, на которую вы ориентируетесь, на вкладке "Проблемы". Таким образом, вы сможете увидеть текущее обсуждение и более подробные шаги о том, как заявить права на нужный вам поддомен.

## Как внести свой вклад

Вы можете представить новые услуги здесь: https://github.com/EdOverflow/can-i-take-over-xyz/issues/new?template=new-entry.md.

Список служб, которые можно проверить (хотя сначала проверьте наличие дубликатов в этом списке), можно найти здесь: https://github.com/EdOverflow/can-i-take-over-xyz/issues/26.

# Все записи

Engine                                        | Status         | Fingerprint                                                             | Discussion                                                    | Documentation
--------------------------------------------- | -------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------
Acquia | Not vulnerable | `Web Site Not Found` |[Issue #103](https://github.com/EdOverflow/can-i-take-over-xyz/issues/103)
Agile CRM | Vulnerable | `Sorry, this page is no longer available.` |[Issue #145](https://github.com/EdOverflow/can-i-take-over-xyz/issues/145)
Airee.ru                             | Vulnerable     | `Ошибка 402. Сервис Айри.рф не оплачен` | [Issue #104](https://github.com/EdOverflow/can-i-take-over-xyz/issues/104) |
Anima | Vulnerable | `If this is your website and you've just created it, try refreshing in a minute` | [Issue #126](https://github.com/EdOverflow/can-i-take-over-xyz/issues/126) | [Anima Documentation](https://docs.animaapp.com/v1/launchpad/08-custom-domain.html)
Akamai                                        | Not vulnerable | | [Issue #13](https://github.com/EdOverflow/can-i-take-over-xyz/issues/13) |
AWS/S3                             | Vulnerable     | `The specified bucket does not exist`                                   | [Issue #36](https://github.com/EdOverflow/can-i-take-over-xyz/issues/36)
AWS/Load Balancer (ELB)                             | Not Vulnerable     | status NXDOMAIN and CNAME pointing to XYZ.elb.amazonaws.com                                 | [Issue #137](https://github.com/EdOverflow/can-i-take-over-xyz/issues/137)
AWS/Elastic Beanstalk                               | Vulnerable         | `404 Not Found`     |                 [Issue #194](https://github.com/EdOverflow/can-i-take-over-xyz/issues/194)
Bitbucket                       | Vulnerable     | `Repository not found`                                                  | [Issue #97](https://github.com/EdOverflow/can-i-take-over-xyz/issues/97)
Campaign Monitor         | Vulnerable     |               `Trying to access your account?`                                                          |  [Issue #275](https://github.com/EdOverflow/can-i-take-over-xyz/issues/275)                                                            | [Support Page](https://help.campaignmonitor.com/custom-domain-names)
Canny | Vulnerable | `Company Not Found` `There is no such company. Did you enter the right URL?` | [Issue #114](https://github.com/EdOverflow/can-i-take-over-xyz/issues/114) |
 Cargo Collective         | Vulnerable     | `404 Not Found` | [Issue #152](https://github.com/EdOverflow/can-i-take-over-xyz/issues/152)                                                                                                                      | [Cargo Support Page](https://support.2.cargocollective.com/Using-a-Third-Party-Domain)
Cloudfront                     | Not vulnerable      | ViewerCertificateException            | [Issue #29](https://github.com/EdOverflow/can-i-take-over-xyz/issues/29) | [Domain Security on Amazon CloudFront](https://aws.amazon.com/blogs/networking-and-content-delivery/continually-enhancing-domain-security-on-amazon-cloudfront/)
Desk                                 | Not vulnerable     | `Please try again or try Desk.com free for 14 days.`                    | [Issue #9](https://github.com/EdOverflow/can-i-take-over-xyz/issues/9)
Digital Ocean | Vulnerable | Domain uses DO name servers with no records in DO. |   |   |
Discourse | Vulnerable | | [Issue #49](https://github.com/EdOverflow/can-i-take-over-xyz/issues/49) | [Hackerone](https://hackerone.com/reports/264494)
Dreamhost | Not Vulnerable | `Site Not Found Well, this is awkward. The site you're looking for is not here.` | [Issue #153](https://github.com/EdOverflow/can-i-take-over-xyz/issues/153) [Issue #5](https://github.com/shifa123/Can-I-take-over-xyz-v2/issues/5v) |
Fastly                             | Not vulnerable     | `Fastly error: unknown domain:`                                         | [Issue #22](https://github.com/EdOverflow/can-i-take-over-xyz/issues/22)
Feedpress                       | Not vulnerable     | `The feed has not been found.`                                          | [Issue #80](https://github.com/EdOverflow/can-i-take-over-xyz/issues/80)
Firebase | Not vulnerable | | [Issue #128](https://github.com/EdOverflow/can-i-take-over-xyz/issues/128) |
Fly.io                             | Vulnerable     | `404 Not Found`                                         | [Issue #101](https://github.com/EdOverflow/can-i-take-over-xyz/issues/101)
Freshdesk                       | Not vulnerable |`We couldn't find servicedesk.victim.tld Maybe this is still fresh! You can claim it now at http://www.freshservice.com/signup`| [Issue #214](https://github.com/EdOverflow/can-i-take-over-xyz/issues/214)| [Freshdesk Support Page](https://support.freshdesk.com/support/solutions/articles/37590-using-a-vanity-support-url-and-pointing-the-cname)
Frontify | Edge case | `404 - Page Not Found` `Oops… looks like you got lost` | [Issue #170](https://github.com/EdOverflow/can-i-take-over-xyz/issues/170) | 
Gemfury | Vulnerable | `404: This page could not be found.` | [Issue #154](https://github.com/EdOverflow/can-i-take-over-xyz/issues/154) | [Article](https://khaledibnalwalid.wordpress.com/2020/06/25/gemfury-subdomain-takeover/)
Getresponse | Vulnerable | `With GetResponse Landing Pages, lead generation has never been easier` | [Issue #235](https://github.com/EdOverflow/can-i-take-over-xyz/issues/235)
Ghost                               | Vulnerable     | `The thing you were looking for is no longer here, or never was`        | [Issue #89](https://github.com/EdOverflow/can-i-take-over-xyz/issues/89)
Github                             | Edge case     | `There isn't a GitHub Pages site here.`                                 | [Issue #37](https://github.com/EdOverflow/can-i-take-over-xyz/issues/37) [Issue #68](https://github.com/EdOverflow/can-i-take-over-xyz/issues/68)
Gitlab                             | Not vulnerable |                                                                         | [HackerOne #312118](https://hackerone.com/reports/312118)
Google Cloud Storage | Not vulnerable |   <?xml version='1.0' encoding='UTF-8'?><Error><Code>NoSuchBucket</Code><Message>The specified bucket does not exist.</Message></Error>   
Google Sites                           | Not vulnerable     | `The requested URL was not found on this server. That’s all we know.`                                                    | [Issue #277](https://github.com/EdOverflow/can-i-take-over-xyz/issues/277) | [Google Support](https://support.google.com/webmasters/answer/9008080?visit_id=637981741431097680-3818919062&rd=2)|
HatenaBlog | vulnerable | `404 Blog is not found`                                                                         |
Help Juice                     | Vulnerable     | `We could not find what you're looking for.`                            |                                                               | [Help Juice Support Page](https://help.helpjuice.com/en_US/using-your-custom-domain/how-to-set-up-a-custom-domain)
Helprace | Vulnerable |  `Alias not configured!` `Admin of this Helprace account needs to set up domain alias`  | [Issue #115](https://github.com/EdOverflow/can-i-take-over-xyz/issues/115)
Help Scout                     | Vulnerable     | `No settings were found for this company:`                              |                                                               | [HelpScout Docs](https://docs.helpscout.net/article/42-setup-custom-domain)
Heroku                             | Edge case     | `No such app`                                                           | [Issue #38](https://github.com/EdOverflow/can-i-take-over-xyz/issues/38)
HubSpot                            | Not vulnerable | `This page isn't available` | [Issue #59](https://github.com/EdOverflow/can-i-take-over-xyz/issues/59)
Instapage | Not vulnerable | | [Issue #73](https://github.com/EdOverflow/can-i-take-over-xyz/issues/73) | |
Intercom                          | Vulnerable     | `Uh oh. That page doesn't exist.`                                         | [Issue #69](https://github.com/EdOverflow/can-i-take-over-xyz/issues/69) | [Help center](https://www.intercom.com/help/)
JetBrains                       | Vulnerable     | `is not a registered InCloud YouTrack`                                  | [PR #107](https://github.com/EdOverflow/can-i-take-over-xyz/pull/107) | [YouTrack InCloud Help Page](https://www.jetbrains.com/help/youtrack/incloud/Domain-Settings.html)
Key CDN                             | Not vulnerable     | | [Issue #112](https://github.com/EdOverflow/can-i-take-over-xyz/issues/112) |
Kinsta                           | Vulnerable     | `No Site For Domain`                                                 |[Issue #48](https://github.com/EdOverflow/can-i-take-over-xyz/issues/48) | [kinsta-add-domain](https://kinsta.com/knowledgebase/add-domain/)
Landingi  | Edge case     | `It looks like you’re lost...` | [Issue #117](https://github.com/EdOverflow/can-i-take-over-xyz/issues/117)
LaunchRock                         | Vulnerable     | `It looks like you may have taken a wrong turn somewhere. Don't worry...it happens to all of us.`                                                 |[Issue #74](https://github.com/EdOverflow/can-i-take-over-xyz/issues/74) | 
Mashery                           | Edge Case | `Unrecognized domain`                                                   | [Issue #14](https://github.com/EdOverflow/can-i-take-over-xyz/issues/14)|  [HackerOne](https://hackerone.com/reports/275714)
Mailchimp  | Not Vulnerable |`We can't find that page It looks like you're trying to reach a page that was built by Mailchimp but is no longer active.` | [Discussion #250](https://github.com/EdOverflow/can-i-take-over-xyz/discussions/250)
Microsoft Azure           | Vulnerable     |  | [Issue #35](https://github.com/EdOverflow/can-i-take-over-xyz/issues/35) |
Netlify | Edge Case | `Not Found - Request ID:`  | [Issue #40](https://github.com/EdOverflow/can-i-take-over-xyz/issues/40) |
Ngrok | Vulnerable | `Tunnel *.ngrok.io not found` | [Issue #92](https://github.com/EdOverflow/can-i-take-over-xyz/issues/92) | [Ngrok Documentation](https://ngrok.com/docs#http-custom-domains)
Pantheon                           | Vulnerable     | `404 error unknown site!`                                                 |[Issue #24](https://github.com/EdOverflow/can-i-take-over-xyz/issues/24) | [Pantheon-Sub-takeover](https://medium.com/@hussain_0x3c/hostile-subdomain-takeover-using-pantheon-ebf4ab813111)
Pingdom | Vulnerable | `Sorry, couldn't find the status page` | [Issue #144](https://github.com/EdOverflow/can-i-take-over-xyz/issues/144) | [Support Page](https://help.pingdom.com/hc/en-us/articles/205386171-Public-Status-Page)
Readme.io | Vulnerable | `Project doesnt exist... yet!` | [Issue #41](https://github.com/EdOverflow/can-i-take-over-xyz/issues/41)
Readthedocs | Vulnerable | `The host 'XYZ' is unknown to Read the Docs` | [Issue #160](https://github.com/EdOverflow/can-i-take-over-xyz/issues/160)
Sendgrid                         | Not vulnerable |                                                                         |
Shopify                           | Edge Case     | `Sorry, this shop is currently unavailable.`                            |[Issue #32](https://github.com/EdOverflow/can-i-take-over-xyz/issues/32) [Issue #46](https://github.com/EdOverflow/can-i-take-over-xyz/issues/46)| [Medium Article](https://medium.com/@thebuckhacker/how-to-do-55-000-subdomain-takeover-in-a-blink-of-an-eye-a94954c3fc75) 
Short.io | Vulnerable| `Link does not exist` | [Issue #260](https://github.com/EdOverflow/can-i-take-over-xyz/issues/260)
SmartJobBoard | Vulnerable | `This job board website is either expired or its domain name is invalid.` | [Issue #139](https://github.com/EdOverflow/can-i-take-over-xyz/issues/139) | [Support Page](https://help.smartjobboard.com/en/articles/1269655-connecting-a-custom-domain-name)
Smartling| Edge Case|`Domain is not configured`  | [Issue #67](https://github.com/EdOverflow/can-i-take-over-xyz/issues/67)
Smugsmug | Vulnerable | | [Issue #60](https://github.com/EdOverflow/can-i-take-over-xyz/issues/60)
Squarespace                   | Not vulnerable |                                                                         |
Statuspage | Not Vulnerable | `Status page pushed a DNS verification in order to prevent malicious takeovers what they mentioned in` [This Doc](https://support.atlassian.com/statuspage/docs/configure-your-dns/) | [PR #105](https://github.com/EdOverflow/can-i-take-over-xyz/pull/105) [PR #171](https://github.com/EdOverflow/can-i-take-over-xyz/pull/171) | [Statuspage documentation](https://help.statuspage.io/knowledge_base/topics/domain-ownership) |          
Strikingly                           | Vulnerable     | `page not found`                                                 |[Issue #58](https://github.com/EdOverflow/can-i-take-over-xyz/issues/58) | [Strikingly-Sub-takeover](https://medium.com/@sherif0x00/takeover-subdomains-pointing-to-strikingly-5e67df80cdfd)
Surge.sh                         | Vulnerable     | `project not found`                                                     |[Issue #198](https://github.com/EdOverflow/can-i-take-over-xyz/issues/198)| [Surge Documentation](https://surge.sh/help/adding-a-custom-domain)
SurveySparrow | Vulnerable | 'Ouch! Account not found' | [Issue #281](https://github.com/EdOverflow/can-i-take-over-xyz/issues/281) |[Custom domain]( https://help.surveysparrow.com/custom-domain)
Tumblr                             | Edge Case     | `Whatever you were looking for doesn't currently exist at this address` | [Issue #240](https://github.com/EdOverflow/can-i-take-over-xyz/issues/240) | [Tumblr Custom Domains](https://www.tumblr.com/docs/en/custom_domains)
Tilda                               | Edge Case | `Please renew your subscription`                                        | [Issue #155](https://github.com/EdOverflow/can-i-take-over-xyz/issues/155) [PR #20](https://github.com/EdOverflow/can-i-take-over-xyz/pull/20)
Uberflip | Vulnerable | `Non-hub domain, The URL you've accessed does not provide a hub.` | [Issue #150](https://github.com/EdOverflow/can-i-take-over-xyz/issues/150) | [Uberflip Documentation](https://help.uberflip.com/hc/en-us/articles/360018786372-Custom-Domain-Set-up-Your-Hub-on-a-Subdomain)
Unbounce                         | Not Vulnerable | `The requested URL was not found on this server.`                       | [Issue #11](https://github.com/EdOverflow/can-i-take-over-xyz/issues/11)
Uptimerobot                           | Vulnerable     | `page not found`                                                 |[Issue #45](https://github.com/EdOverflow/can-i-take-over-xyz/issues/45) | [Uptimerobot-Sub-takeover](https://exploit.linuxsec.org/uptimerobot-com-custom-domain-subdomain-takeover/)
UserVoice                       | Not Vulnerable     | `This UserVoice subdomain is currently available!`                      |[Issue #163](https://github.com/EdOverflow/can-i-take-over-xyz/issues/163)
Vercel| Not Vulnerable| The deployment could not be found on Vercel.` |[Issue #183](https://github.com/EdOverflow/can-i-take-over-xyz/issues/183)
Webflow                           | Edge Case     | `The page you are looking for doesn't exist or has been moved.` |[Issue #44](https://github.com/EdOverflow/can-i-take-over-xyz/issues/44) |[forum webflow](https://forum.webflow.com/t/hosting-a-subdomain-on-webflow/59201)
Wix                           | Edge Case     | `Looks Like This Domain Isn't Connected To A Website Yet!` |[Issue #231](https://github.com/EdOverflow/can-i-take-over-xyz/issues/231) 
Wordpress                       | Vulnerable     | `Do you want to register *.wordpress.com?`                              | [PR #176](https://github.com/EdOverflow/can-i-take-over-xyz/pull/176)|
Worksites | Vulnerable | `Hello! Sorry, but the website you&rsquo;re looking for doesn&rsquo;t exist.` | [Issue #142](https://github.com/EdOverflow/can-i-take-over-xyz/issues/142) | 
WP Engine                       | Not vulnerable |                                                                         |
Zendesk                           | Not vulnerable     | `Help Center Closed`                                                    | [Issue #23](https://github.com/EdOverflow/can-i-take-over-xyz/issues/23) | [Zendesk Support](https://support.zendesk.com/hc/en-us/articles/203664356-Changing-the-address-of-your-Help-Center-subdomain-host-mapping-)
