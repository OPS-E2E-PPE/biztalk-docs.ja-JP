---
title: "シングル サインオン: イベント 10547 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6162461b1eb04993ca681049fe1fbb797ca014
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10547"></a>シングル サインオン: イベント 10547
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10547|  
|イベント ソース|ENTSSO|  
|コンポーネント|CO|  
|シンボル名|SSO_WARN_UPDATE_FAILED|  
|メッセージ テキスト|再暗号化の間に SSO データベース内の資格情報を更新できませんでした|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、新しい暗号化の結果で資格情報を更新できなかったことを示します。 新しいシークレットの入力または古いシークレットの復元によってマスター シークレットを変更すると、SSO データベースに格納されている古いシークレットで暗号化されたすべてのシークレットが復号化され、新しいシークレットで再暗号化されます。 再暗号化の過程で資格情報が削除された場合、このイベントが発生する可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   別の再暗号化が行われるまでしばらく待ちます。自動的に行われない場合は、SSO サービスを再起動すると、必要な場合は新しい再暗号化が実行されます。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO について](../core/understanding-sso.md)