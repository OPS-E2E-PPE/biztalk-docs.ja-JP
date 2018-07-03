---
title: 制御番号が重複しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 331ad173-29b3-427c-8104-60d80c580a5a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcfd1a10b836ec593b6aa94a87d8145d6e2ebaaf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967891"
---
# <a name="duplicate-control-number"></a>制御番号が重複しています
## <a name="details"></a>詳細  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |                                制御番号が重複しています                                |

## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI 受信パイプラインの中に、以前受信したインターチェンジと同じインターチェンジ制御番号、グループ制御番号、またはトランザクション セット制御番号が含まれていたため、EDI 受信パイプラインが受信インターチェンジを処理できなかったことを示します。 重複している制御番号のチェックが有効になっている限り、この重複はエラーになります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  

- 対応する重複した制御番号の確認が有効になっている場合は、BizTalk Server に送信したインターチェンジで前のインターチェンジと同じインターチェンジ制御番号、グループ制御番号、またはトランザクション セット制御番号が使用されていないことを確認します。  

- 重複する制御番号の確認を無効化します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、該当するパーティを右クリックして、インターチェンジ送信者であるパーティの [EDIFACT インターチェンジ処理のプロパティ] または [X12 インターチェンジ処理のプロパティ] ダイアログ ボックスを開きます。 EDIFACT インターチェンジに対する確認を無効化するには、[重複している UNB5 (インターチェンジ制御番号) を確認する]、[インターチェンジ内で重複している UNG5 (グループ制御番号) を確認する]、[グループ内で重複している UNH1 (トランザクション セット参照番号) を確認する] のいずれかのプロパティをオフにします。 X12 インターチェンジに対する確認を無効化するには、[重複している ISA13 (インターチェンジ制御番号) を確認する]、[インターチェンジ内で重複している GS6 (グループ制御番号) を確認する]、[グループ内で重複している ST2 (トランザクション セット制御番号] のいずれかのプロパティをオフにします。
