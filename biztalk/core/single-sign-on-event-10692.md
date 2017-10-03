---
title: "シングル サインオン: イベント 10692 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78a476ca-32eb-4f37-a807-25850503db6e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2dce820864338cd5ba3b8ecf4a469ae75550a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10692"></a>シングル サインオン: イベント 10692
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10692|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_REPLAY_ACCESS_DENIED|  
|メッセージ テキスト|元の呼び出し元がアダプターのアクセス アカウントのメンバーではなくなったため、外部パスワード変更を再生できません。%r<br /><br /> 再生ファイル: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> 最初の呼び出し元: %3 %r<br /><br /> アクセス アカウント: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、SSO が SSO データベースとの接続を再び確立したが、当初変更を指定したアカウントが有効ではなくなったため、再生ファイルで指定された (SSO データベースでの) 変更を実行できなかったことを示します。  
  
 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期](../core/password-synchronization2.md)