---
title: 'シングル サインオン: イベント 10532 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a9d477ec54a3c959f2afdf4c687c65b88523ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269754"
---
# <a name="single-sign-on-event-10532"></a>シングル サインオン: イベント 10532
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10532|  
|イベント ソース|ENTSSO|  
|コンポーネント|CO|  
|シンボル名|SSO_WARN_LOST_SECRET_SERVER|  
|メッセージ テキスト|マスター シークレットを取得できませんでした。 マスター シークレット サーバー名が正しいこと、および利用可能であることを確認してください。%r<br /><br /> シークレット サーバー名: %1 %r<br /><br /> エラー コード: %2|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、マスター シークレットの取得要求が失敗したことを示します。 エンタープライズ シングル サインオン サービスがサーバー上で実行されていないことが原因である可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。  
  
-   マスター シークレット サーバー名が正しいことを確認します。  
  
-   マスター シークレット サーバーがオンラインであり、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  
  
-   [マスタ シークレットの管理](../core/managing-the-master-secret.md)