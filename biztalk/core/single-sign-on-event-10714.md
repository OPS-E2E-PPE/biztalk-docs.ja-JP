---
title: "シングル サインオン: イベント 10714 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59d8509f-cc3e-40fa-ba3d-3dcb0e73c67a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba63ab9197dcf9629f03f3d6c96f064345aaa46e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10714"></a>シングル サインオン: イベント 10714
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10714|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED|  
|メッセージ テキスト|再試行の有効期限が切れたので、通知を破棄しています。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプタ: %2|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、パスワード同期通知の再試行の有効期限が切れ、通知が破棄されたことを示します。  
  
 パスワード変更 (Windows から外部システムへの変更) はパスワード同期アダプターに配信され、パスワード同期アダプターはパスワード変更が正常に処理されたことを確認します。 指定された期間内にパスワード変更が行われなかった場合や、変更中に別の問題が発生した場合は、パスワード変更が再びパスワード同期アダプターに配信されます。 この処理が決められた回数 (最大試行回数) だけ実行された後、パスワード変更通知は破棄されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期](../core/password-synchronization2.md)