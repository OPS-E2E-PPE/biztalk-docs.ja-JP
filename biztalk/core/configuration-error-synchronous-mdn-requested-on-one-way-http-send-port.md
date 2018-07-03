---
title: 構成エラー。 送信ポートで一方向の HTTP 要求されている同期 MDN |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd38eb3-321f-4738-b35e-390f4f54673e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0118789db8e45b096f3852aef3487416d388961d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014147"
---
# <a name="configuration-error-synchronous-mdn-requested-on-one-way-http-send-port"></a>構成エラー。 一方向の HTTP 送信ポートで同期 MDN が要求されました
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
 このエラー/警告/情報イベントは、AS2 メッセージを送信した HTTP 送信ポートが一方向ポートであったため、BizTalk Server が AS2 メッセージ送信後の同期 MDN を受信できなかったことを示します。 ポートから送信された AS2 メッセージへの応答として返される同期 MDN を処理するには、双方向の送信請求 - 応答の送信ポートが必要です。 この場合、AS2 メッセージの受信者としてのパーティの構成で [MDN を要求する] プロパティがオンになっており、[非同期 MDN を要求する] プロパティがオフになっているため、MDN は同期的に返される必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 メッセージの送信元の送信ポートを、一方向の送信ポートではなく静的な送信請求 - 応答の送信ポートに変更します。 送信請求 - 応答の送信ポートの受信パイプラインを AS2EdiReceive (EDI インターチェンジ用) または AS2Receive (非 EDI インターチェンジ用) に設定します。