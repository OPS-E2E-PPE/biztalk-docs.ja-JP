---
title: "シングル サインオン: イベント 10669 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e88a583d-7385-42dd-841e-aa2d2215dd69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 334180225d47cb9a86577cab75490ea0b6f2225a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10669"></a>シングル サインオン: イベント 10669
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10669|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED|  
|メッセージ テキスト|Windows パスワードを変更できませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> Windows アカウント: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、SSO が Windows のパスワードを変更できなかったことを示します。 SSO は、Win32 の関数 NetUserChangePassword を呼び出して、マッピングと関連付けられた Windows のパスワードを変更します。 この関数が失敗すると、このエラー メッセージが発生します。 エラー コードは、NetUserChangePassword から返されたものです。 詳細については、MSDN でこの関数のドキュメントを参照してください。 原因として最も可能性が高いのは、古いパスワードが正しくなかったか、または新しいパスワードが必要な Windows パスワード ポリシーを満たしていない場合です。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   古いパスワードを確認します。 古いパスワードが正しくない場合は、コマンド ライン ツールまたは管理 MMC を使用して、SSO データベースを手動で設定できます。  
  
-   新しいパスワードが必要な Windows パスワード ポリシーを満たしていることを確認します。 パスワードが Windows パスワード ポリシーを満たしていない場合は、パスワード フィルターの使用を検討します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [パスワード同期](../core/password-synchronization2.md)