---
title: オーケストレーション (BizTalk Server サンプル) を参加させる |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, enlisting
- examples, orchestrations
ms.assetid: d8d53e59-2313-40dd-a278-0a29d8eb4ce8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70276a30004c1a21f95a3e2ff43a28209deea87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389073"
---
# <a name="enlist-orchestration-biztalk-server-sample"></a>オーケストレーション (BizTalk Server サンプル) を参加させる
オーケストレーションの参加サンプルでは、ホストに BizTalk Server オーケストレーションを参加させる方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、Windows Management Instrumentation (WMI) オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンと Visual c# バージョンにアクセスする、 **System.Management**によって提供されるオブジェクト.NET Framework です。 これらのバージョンのどちらも最終的には、次の操作を実行する BizTalk Server WMI プロバイダーにアクセスします。  
  
-   オーケストレーション名とアセンブリ名を指定するには、特定のクエリには、BizTalk Server オーケストレーションが展開されています。  
  
-   既定のホストにオーケストレーションを参加させます。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 サンプルは、次の SDK の場所に配置されます。  
  
- VBScript バージョン:\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
- VisusalC#バージョン。\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\CSharp\  
  
  次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー。<br /><br /> EnlistOrch.vbs|ホストに参加させるオーケストレーションを指定するパラメーターを取る VBScript ファイル。|  
|\CSharp フォルダー。<br /><br /> App.ico、AssemblyInfo.cs、BTSampleEnlistOrc.csproj、BTSampleEnlistOrc.sln、EnlistOrc.cs|プロジェクト、ソリューション、およびビジュアルを構築するためのソース ファイルC#ホストに参加させるオーケストレーションを指定するパラメーターを受け取るコマンド ライン アプリケーションです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 オーケストレーションの参加サンプルの VBScript バージョンは、ビルドまたは初期化する必要はありませんは、1 つ Visual Basic スクリプト ファイルで構成されます。  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a>ビジュアルを構築するC#オーケストレーションの参加サンプルのバージョン  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション ファイル BTSampleEnlistOrc.sln を開きます。  
  
2. **ビルド** メニューのをクリックして**ソリューションのビルド**します。  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a>オーケストレーションの参加のサンプルを実行します。  
  
1.  コマンド ウィンドウで、ビジュアルの VBScript バージョンとの実行を計画しているかどうかに応じて、次のフォルダーのいずれかに移動します。C#のこのバージョンのサンプルをそれぞれ。  
  
     \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
     \<*パスのサンプル*\>AdminWMIEnlist OrchestrationCSharpbinDebug  
  
2.  Cscript プログラムを使用して enlistorch.vbs を実行するか、ビジュアルの VBScript バージョンとの実行を計画しているかどうかに応じて、ファイル EnlistOrc.exe を実行C#のこのバージョンのサンプル、それぞれします。 いずれの場合は、次のコマンドライン引数を渡します。  
  
    -   **\<** ***OrchestrationName* \>.** 参加させるオーケストレーションの名前。  
  
    -   **\<** ***AssemblyName* \>.** オーケストレーションが展開されているアセンブリの名前。 アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。  
  
         以下に例を示します。(VBScript) の場合:  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         -または-(Visual c#)。  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a>コメント  
 すべてのタスクで実行できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジュアルを使用して、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することもC#にアクセスする、 **System.Management**オブジェクト.NET Framework によって提供されます。  
  
 スクリプト ファイル EnlistOrch.vbs およびビジュアルC#ソース ファイル EnlistOrc.cs には、実行する操作についての説明と詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)