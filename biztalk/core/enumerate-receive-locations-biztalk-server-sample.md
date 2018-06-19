---
title: 列挙の受信場所 (BizTalk Server サンプル) |Microsoft ドキュメント
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
ms.openlocfilehash: 82fcdc400395d7bbfd6de8f9bc0fca85114a25dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969080"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a>列挙の受信場所 (BizTalk Server サンプル)
受信場所の列挙サンプルでは、1 つ以上の受信場所に関する詳細情報を取得する方法を説明します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルには、Windows WMI オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンとにアクセスする Visual c# バージョンが含まれています、 **System.Management** .NET Framework によって提供されるオブジェクト。 いずれのバージョンも、最終的に BizTalk Server WMI プロバイダにアクセスして次の操作を実行します。  
  
-   名前を指定して、構成済みの受信場所のセット、または特定の受信場所をクエリします。  
  
-   対象の各受信場所に関する詳細情報を取得および表示します。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、次の SDK の場所にあります。  
  
-   VBScript バージョン: \<*サンプル パス*\>\Admin\WMI\Enumerate Receive Locations\VBScript\  
  
-   Visual c# バージョン: \<*サンプル パス*\>\Admin\WMI\Enumerate Receive Locations\CSharp\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> EnumRecLocs.vbs|構成済みのすべての受信場所についての詳細情報を取得する VBScript ファイル|  
|\CSharp フォルダー内のファイル : <br /><br /> App.ico、AssemblyInfo.cs、BTSampleEnumerateRLs.csproj、BTSampleEnumerateRLs.sln、および EnumRLs.cs|構成済みのすべての受信場所または特定の受信場所についての詳細情報を取得する Visual C# コマンド ライン アプリケーションを構築するためのプロジェクト、ソリューション、およびソース ファイル|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 受信場所の列挙サンプルの VBScript バージョンは、構築または初期化が不要な 1 つの Visual Basic スクリプト ファイルで構成されます。  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a>受信場所の列挙サンプルの Visual C# バージョンを構築するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル BTSampleEnumerateRLs.sln を開きます。  
  
2.  **ビルド** メニューのをクリックして**ソリューションのビルド**です。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a>受信場所の列挙サンプルを実行するには  
  
1.  コマンド ウィンドウで、このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、次のフォルダのどちらかに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Enumerate 受信 Locations\VBScript\  
  
     \<*パスのサンプル*\>\Admin\WMI\Enumerate 受信 Locations\CSharp\bin\Debug\  
  
2.  このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、EnumRecLocs.vbs (cscript プログラムを使用) または EnumRl.exe を実行します。 Visual C# バージョンの場合は、次の 2 つのコマンド ライン引数の 1 つを渡します。  
  
    -   **\<ReceiveLocationName\>です。** 詳細情報を表示する受信場所の名前です。 受信場所名に空白が含まれている場合は、名前を引用符で囲みます。  
  
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
 実行できるすべてのタスク、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] # を使用して Visual C にアクセスして、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することも、 **System.Management**提供されるオブジェクト.NET framework。  
  
 スクリプト ファイル EnumRecLocs.vbs および Visual C# ソース ファイル EnumRLs.cs には、実行する操作について説明する詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)