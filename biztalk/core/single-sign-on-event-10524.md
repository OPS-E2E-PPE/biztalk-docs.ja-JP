---
title: 'シングル サインオン: イベント 10524 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55e26da3-f67f-4f87-92e5-2f8765b19989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c79da37aaa54f44daaa39048fcdf58e67064f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271842"
---
# <a name="single-sign-on-event-10524"></a>シングル サインオン: イベント 10524
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10524|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_RESTORE_SECRET_FAILED|  
|メッセージ テキスト|マスター シークレットを復元できませんでした。%r<br /><br /> ファイル名: %1 %r<br /><br /> 現在の MSID: %2 %r<br /><br /> 以前の MSID: %3 %r<br /><br /> クライアント ユーザー: %4 %r<br /><br /> エラー コード: %5|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、ユーザーがバックアップ ファイルからマスター シークレットを復元しようとしたが、失敗したことを示します。 これは、問題がある場合のためのアクセス許可 (マスタ シークレットの復元には、SSO 管理者である必要があります) またはバックアップ ファイルのファイルの破損原因として考えられます。 これらの場合、アプリケーション イベント ログに関連するメッセージがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。  
  
-   適切な SSO 管理者のアクセス許可があることを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)  
  
-   [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)  
  
-   [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)