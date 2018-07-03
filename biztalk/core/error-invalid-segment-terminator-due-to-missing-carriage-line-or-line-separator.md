---
title: インターチェンジで構造エラーが見つかりました。 可能性の高い原因は復帰がないため、無効なセグメントの終端記号と、または改行区切り |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035e37d5-d4a8-49d0-8d75-3bcf2426cac7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e1d3c90d69b3e482ac570538f5dcc6997a63aea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988771"
---
# <a name="the-interchange-had-structural-error-a-likely-cause-is-invalid-segment-terminator-due-to-missing-carriage-line-and-or-line-feed-seperators"></a>インターチェンジで構造エラーが見つかりました。 可能性の高い原因は復帰がないため、無効なセグメントの終端記号と、または改行区切り
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                   |
| 製品バージョン |                                                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                                               |
|    イベント ID     |                                                                                                                                           -                                                                                                                                           |
|  イベント ソース   |                                                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                                                 |
|    コンポーネント    |                                                                                                                                      EDI エンジン                                                                                                                                       |
|  シンボル名  |                                                                                                                        EfactInterchangeStructuralErrorAfterUnb                                                                                                                        |
|  メッセージ テキスト   | Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。 復帰や改行の区切り記号がないため、セグメント終端記号が無効になっていることが原因として考えられます。 エラー発生後の部分は中断されています。詳細については、保留キューを参照してください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ内のセグメントに必要なセグメント終端記号がなかったため、受信パイプライン、送信パイプライン、またはバッチ処理オーケストレーションで EDIFACT インターチェンジを処理できなかったことを示します。 受信インターチェンジの場合、区切り記号は UNA セグメントで識別されます。UNA セグメントがない場合は、EfactDelimiters パイプライン プロパティで識別されます。 送信インターチェンジの場合、区切り記号は [EDI のプロパティ] ダイアログ ボックスの [UNA セグメントの定義] ページで識別されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのすべてのセグメントに必要なセグメント終端記号が含まれていることを確認し、インターチェンジを再送信します。