---
title: "アグリーメントにアクセスできません受信者 id を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f41b126ca0ebb96716f21381d2e1681ea59bd414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a>受信者 ID を使用してアグリーメントにアクセスできません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|UnableToLocateAS2PartyByPartyNameError|  
|メッセージ テキスト|アグリーメントにアクセスできません受信者 id を使用して: {0}|  
  
## <a name="explanation"></a>説明  
 このエラーは、送信パイプラインで送信 AS2 メッセージの送信先パーティを決定できなかったことを示します。送信パイプラインは、送信メッセージの AS2To コンテキスト プロパティまたは Http.UserHttpHeaders コンテキスト プロパティの AS2To プロパティと、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページにある AS2-To プロパティのパーティの名前を照合できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページにある AS2-To プロパティを、エラーになった AS2 メッセージに関連付けられた適切なパーティ名に設定します。