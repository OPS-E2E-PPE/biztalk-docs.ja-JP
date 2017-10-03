---
title: "BizTalk Server ツールのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 038a5f5c-d6eb-42db-88d6-70f3deba7a8a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7aedd8977042d15176781b0595bd5bb225a2fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-tools"></a>BizTalk Server ツールのトラブルシューティング
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属するツールの使用時に発生する一般的な問題に関する情報をまとめて提供します。  
  
## <a name="known-issues"></a>既知の問題  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a>UAC をサポートする Windows システムでは、BizTalk Server のツールおよびユーティリティが正しく機能しない場合がある  
 **問題**  
  
 ユーザー アカウント制御 (UAC) をサポートするシステムに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属するツールが正常に起動しない、または正しく機能しない場合があります。  
  
 **原因**  
  
 特定の特権レベルのフラグが設定されたアプリケーションを実行する場合、アプリケーションを実行するユーザーのレベルよりも高いレベルが必要なときは、UAC のメッセージが表示され、ユーザーは一時的にアプリケーション特権を必要なレベルに昇格できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属するツールは、特権昇格の自動要求を可能にする正しいフラグが設定されていないため、アプリケーションを実行しているユーザーの現在の特権レベルで実行を試み、より高いレベルが要求される場合はエラーになります。  
  
 **解決策**  
  
 この問題を解決するには、すべての BizTalk Server ツールを管理者特権で実行します。 管理者特権を持つ、ツールを実行するアプリケーションを右クリックし **管理者として実行**です。  
  
 ユーザー アカウント制御の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167)です。  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a>BizTalk マッパー ツールボックスが空のように見える場合がある  
 **問題**  
  
 Visual Studio でマッパー ツールボックスを開いたときに、ツールボックスに Functoid がまったく表示されないことがあります。  
  
 **原因**  
  
 Visual Studio のアドインや修正プログラムのインストールまたはアンインストールによる破損の可能性があります。  
  
 **解決策**  
  
 この問題を解決するには、次のようにします。  
  
1.  Visual Studio の実行中のすべてのインスタンスを閉じます。  
  
2.  開始**Visual Studio コマンド プロンプト**を管理者として。  
  
3.  コマンド プロンプトで、次のコマンドを入力します。  
  
    ```  
    devenv.exe /setup  
    ```