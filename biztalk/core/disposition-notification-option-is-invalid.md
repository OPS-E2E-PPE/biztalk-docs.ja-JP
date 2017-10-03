---
title: "廃棄通知オプションが正しくない |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1b807a8-eec9-45a5-83cc-075c91b4bc9e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72221c98dfcac42f735f63a1ce01a7c26bc45387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="disposition-notification-option-is-invalid"></a>Disposition-Notification-Option が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|-|  
|メッセージ テキスト|廃棄-通知-オプションの値:"{0}"が無効です。 {1}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、Disposition-Notification-Option ヘッダーが無効だったため、AS2 受信パイプラインが MDN を生成できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 メッセージの Disposition-Notification-Option ヘッダーが RFC 4130「MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」に記載されている構文に準拠していることを確認します。 Signed-Receipt-Protocol ヘッダーが "optional" または "pcks7-signature" に設定され、Signed-Receipt-MICAlg ヘッダーが "optional"、"MD5"、または "SHA1" に設定されていることを確認します  (これらのヘッダーは、どちらも Disposition-Notification-Option ヘッダーに含まれています)。