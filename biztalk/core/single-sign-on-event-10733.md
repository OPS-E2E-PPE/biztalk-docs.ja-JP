---
title: "シングル サインオン: イベント 10733 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1387d7c853bba91bea429470d9a615e065a6e8dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10733"></a>シングル サインオン: イベント 10733
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10733|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_SET_WINDOWS_PASSWORD|  
|メッセージ テキスト|SSO データベースの Windows パスワードを更新できませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: %2\\%3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、パスワード同期によって、SSO データベース内の指定された Windows アカウント パスワードを更新できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。  
  
-   指定したアカウントのパスワードが有効な Windows パスワードであることを確認します。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期](../core/password-synchronization2.md)