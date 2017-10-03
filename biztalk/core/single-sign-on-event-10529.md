---
title: "シングル サインオン: イベント 10529 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75ed70e0-8458-4736-883f-a4536f094dc0
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f33c0e475f9b54b5fc0a5d5415736d9717ccdf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10529"></a>シングル サインオン: イベント 10529
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10529|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_INFO_GOT_CURRENT_SECRET|  
|メッセージ テキスト|マスター シークレット サーバーから現在のシークレットを取得しました。%r<br /><br /> シークレット サーバー名: %1 %r<br /><br /> MSID: %2|  
  
## <a name="explanation"></a>説明  
 この情報イベントは、SSO がマスター シークレット サーバーにマスター シークレットを要求したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
  
-   ユーザーの操作は必要ありません。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  
  
-   [マスタ シークレットの管理](../core/managing-the-master-secret.md)