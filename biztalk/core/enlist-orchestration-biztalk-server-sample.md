---
title: オーケストレーション (BizTalk Server サンプル) を参加させる |Microsoft ドキュメント
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
ms.openlocfilehash: 6e8d85a49b410f0571e8e9cb0be816f1feda139e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968865"
---
# <a name="enlist-orchestration-biztalk-server-sample"></a>オーケストレーション (BizTalk Server サンプル) を参加させる
オーケストレーションの参加のサンプルは、BizTalk Server オーケストレーションをホストに参加させる方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルには、Windows Management Instrumentation (WMI) オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンとにアクセスする Visual c# バージョンが含まれています、 **System.Management**によって提供されるオブジェクト.NET Framework。 いずれのバージョンも、最終的に BizTalk Server WMI プロバイダにアクセスして次の操作を実行します。  
  
-   オーケストレーション名とアセンブリ名を受け取ると、展開された特定の BizTalk Server オーケストレーションに対するクエリを実行します。  
  
-   そのオーケストレーションを既定のホストに参加させます。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、次の SDK の場所にあります。  
  
-   VBScript バージョン: \<*サンプル パス*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
-   Visusal c# バージョン: \<*サンプル パス*\>\Admin\WMI\Enlist Orchestration\CSharp\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> EnlistOrch.vbs|ホストに参加させるオーケストレーションを指定するパラメータを受け取る VBScript ファイルです。|  
|\CSharp フォルダー内のファイル : <br /><br /> App.ico、AssemblyInfo.cs、BTSampleEnlistOrc.csproj、BTSampleEnlistOrc.sln、EnlistOrc.cs|ホストに参加させるオーケストレーションを指定するパラメータを受け取る Visual C# コマンド ライン アプリケーションを構築するための、プロジェクト、ソリューション、ソース ファイルです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 オーケストレーションの参加サンプルの VBScript バージョンは、構築または初期化が不要な 1 つの Visual Basic スクリプト ファイルで構成されます。  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a>オーケストレーションの参加サンプルの Visual C# バージョンを構築するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル BTSampleEnlistOrc.sln を開きます。  
  
2.  **ビルド** メニューのをクリックして**ソリューションのビルド**です。  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a>オーケストレーションの参加のサンプルを実行するには  
  
1.  コマンド ウィンドウで、このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、それぞれ以下のいずれかのフォルダに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
     \<*パスのサンプル*\>AdminWMIEnlist OrchestrationCSharpbinDebug  
  
2.  このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、cscript プログラムを使用して EnlistOrch.vbs を実行するか、ファイル EnlistOrc.exe を実行します。 どちらの場合にも、以下のコマンド ライン引数を渡します。  
  
    -   **\<** ***OrchestrationName* \>です。** 参加させるオーケストレーションの名前。  
  
    -   **\<** ***AssemblyName* \>です。** オーケストレーションが展開されているアセンブリの名前。 アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。  
  
         例: (VBScript)。  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         または (Visual C#):  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a>コメント  
 実行できるすべてのタスク、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] # を使用して Visual C にアクセスして、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することも、 **System.Management**提供されるオブジェクト.NET framework。  
  
 スクリプト ファイル EnlistOrch.vbs および Visual C# ソース ファイル EnlistOrc.cs には、実行する操作について説明する詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)