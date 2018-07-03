---
title: 列挙の受信場所 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enumerating
- examples, receive locations
ms.assetid: 27ff8ac6-7e8e-4dde-84d1-d21bf417ddd7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f92e279ce53f068657e46912eb93093728e3185
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021257"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a>列挙の受信場所 (BizTalk Server サンプル)
受信場所の列挙サンプルでは、1 つ以上の受信場所に関する詳細情報を取得する方法を説明します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、Windows WMI オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンと Visual c# バージョンにアクセスする、 **System.Management** .NET Framework で提供されているオブジェクト。 いずれのバージョンも、最終的に BizTalk Server WMI プロバイダにアクセスして次の操作を実行します。  
  
-   名前を指定して、構成済みの受信場所のセット、または特定の受信場所をクエリします。  
  
-   対象の各受信場所に関する詳細情報を取得および表示します。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、次の SDK の場所にあります。  
  
- VBScript バージョン: \<*サンプル パス*\>\Admin\WMI\Enumerate Receive Locations\VBScript\  
  
- Visual c# バージョン: \<*サンプル パス*\>\Admin\WMI\Enumerate Receive Locations\CSharp\  
  
  次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> EnumRecLocs.vbs|構成済みのすべての受信場所についての詳細情報を取得する VBScript ファイル|  
|\CSharp フォルダー内のファイル : <br /><br /> App.ico、AssemblyInfo.cs、BTSampleEnumerateRLs.csproj、BTSampleEnumerateRLs.sln、および EnumRLs.cs|構成済みのすべての受信場所または特定の受信場所についての詳細情報を取得する Visual C# コマンド ライン アプリケーションを構築するためのプロジェクト、ソリューション、およびソース ファイル|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 受信場所の列挙サンプルの VBScript バージョンは、構築または初期化が不要な 1 つの Visual Basic スクリプト ファイルで構成されます。  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a>受信場所の列挙サンプルの Visual C# バージョンを構築するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル BTSampleEnumerateRLs.sln を開きます。  
  
2. **ビルド** メニューのをクリックして**ソリューションのビルド**します。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a>受信場所の列挙サンプルを実行するには  
  
1.  コマンド ウィンドウで、このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、次のフォルダのどちらかに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\VBScript\ の受信  
  
     \<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\CSharp\bin\Debug\ の受信  
  
2.  このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、EnumRecLocs.vbs (cscript プログラムを使用) または EnumRl.exe を実行します。 Visual C# バージョンの場合は、次の 2 つのコマンド ライン引数の 1 つを渡します。  
  
    -   **\<ReceiveLocationName\>します。** 詳細情報を表示する受信場所の名前です。 受信場所名に空白が含まれている場合は、名前を引用符で囲みます。  
  
    -   **/?.** ヘルプを表示します。  
  
         例 (VBScript):  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         または (Visual C#):  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         または (Visual C#):  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  このサンプルの VBScript バージョンでは、コマンド ライン パラメータを使用できないため、構成済みのすべての受信場所についての詳細情報を取得および表示することしかできません。  
  
## <a name="comments"></a>コメント  
 すべてのタスクで実行できる、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] # を使用して Visual C にアクセスして、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することも、 **System.Management**提供されているオブジェクト.NET framework です。  
  
 スクリプト ファイル EnumRecLocs.vbs および Visual C# ソース ファイル EnumRLs.cs には、実行する操作について説明する詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)