---
title: BizTalk Server ツールのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 038a5f5c-d6eb-42db-88d6-70f3deba7a8a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b492c4ee6d22c1eb360f24c60efee1c1106d3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292924"
---
# <a name="troubleshooting-biztalk-server-tools"></a>BizTalk Server ツールのトラブルシューティング
このトピックでは、1 か所に含まれているツールを使用しているときに発生する一般的な問題について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="known-issues"></a>既知の問題  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a>BizTalk Server のツールとユーティリティでは、その UAC をサポートする Windows システムでは正しく機能しない可能性があります。  
 **問題**  
  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ユーザー アカウント制御 (UAC) に付属のツールをサポートするシステムがインストールされている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が正常に起動しない可能性がありますまたは正しく機能しない可能性があります。  
  
 **原因**  
  
 アプリケーションを実行してフラグが設定された特定の特権レベルでは、必要なレベルが、アプリケーションを実行しているユーザーの場合よりも高い場合、UAC がプロンプトにアプリケーション特権を一時的に昇格することができますが表示されます、必要なレベルです。 付属のツール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ツールは、アプリケーションを実行しているユーザーの現在の特権レベルで実行しようしより高い権限レベルがある場合は失敗するために特権の昇格を自動的に要求を有効にする適切なフラグがありません必須。  
  
 **解決方法**  
  
 この問題を解決するには、管理者特権を持つすべての BizTalk Server ツールを実行します。 管理者特権を持つ、ツールを実行するアプリケーションを右クリックし、**管理者として実行**します。  
  
 ユーザー アカウント制御の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167)します。  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a>BizTalk マッパー ツールボックスが空ある場合があります。  
 **問題**  
  
 場合によっては、Visual Studio でマッパー ツールボックスを開くも、ツールボックスに functoid がまったくは表示されません。  
  
 **原因**  
  
 Visual Studio のアドインや修正プログラムのインストール/アンインストールによる破損があります。  
  
 **解決方法**  
  
 この問題を解決するには、次のようにします。  
  
1.  Visual Studio の実行中のすべてのインスタンスを閉じます。  
  
2.  開始**Visual Studio コマンド プロンプト**に管理者として。  
  
3.  コマンド プロンプトで、次のコマンドを入力します。  
  
    ```  
    devenv.exe /setup  
    ```