---
title: 構成エラー。 受信ポートで一方向の HTTP 要求されている同期 MDN |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f140c7a4-46bf-4557-9679-cdaf2fbe66f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1d0d6e78830c06c11c4c6f54789ba522cfaf366
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004731"
---
# <a name="configuration-error-synchronous-mdn-requested-on-a-one-way-http-receive-port"></a>構成エラー。 一方向の HTTP 受信ポートで同期 MDN が要求されました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |       構成エラー。 一方向の HTTP 送信ポートで同期 MDN が要求されました。        |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信 AS2 メッセージを処理した HTTP 受信ポートが一方向ポートだったため、BizTalk Server が AS2 メッセージの受信後に同期 MDN を返すことができなかったことを示します。 受信 AS2 メッセージに応答して同期 MDN を返すには、双方向の要求 - 応答受信ポートが必要です。 この場合、AS2 メッセージに Disposition-Notification-To ヘッダーが含まれているか、または AS2 メッセージ送信者としてのパーティの構成で、[受信メッセージのプロパティをオーバーライドする] プロパティがオン、[MDN の生成] プロパティがオン、[MDN を非同期に送信する] プロパティがオフになっているため、MDN は同期的に返される必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 メッセージを受信している受信ポートを、一方向の受信ポートとするのではなく、要求 - 応答の受信ポートに変更します。 要求 - 応答の受信場所の送信パイプラインを、EDI インターチェンジに対しては AS2EdiSend とし、非 EDI インターチェンジに対しては AS2Send に設定します。