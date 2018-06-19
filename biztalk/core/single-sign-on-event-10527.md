---
title: 'シングル サインオン: イベント 10527 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf1785361ad343b3da4c7dc07b6a73a362fa14d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270202"
---
# <a name="single-sign-on-event-10527"></a>シングル サインオン: イベント 10527
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10527|  
|イベント ソース|ENTSSO|  
|コンポーネント|0|  
|シンボル名|SSO_ERROR_GET_SECRET_FAILED|  
|メッセージ テキスト|マスター シークレットの取得要求が失敗しました。%r<br /><br /> シークレット番号: %1 %r<br /><br /> クライアント ユーザー: %2 %r<br /><br /> クライアント コンピューターの場合: %3 %r<br /><br /> 追跡 ID: %4 %r<br /><br /> エラー コード: %5|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、マスター シークレットの取得要求が失敗したことを示します。 これらの場合、アプリケーション イベント ログに関連するメッセージがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  
  
-   [マスタ シークレットの管理](../core/managing-the-master-secret.md)