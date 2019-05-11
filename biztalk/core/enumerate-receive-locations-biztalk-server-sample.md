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
ms.openlocfilehash: 7941cffb7e796c02b84c2dbd686fa20edbe9c8df
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530764"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a>列挙の受信場所 (BizTalk Server サンプル)
受信場所の列挙サンプルでは、いずれかに関する詳細を取得または以上の受信場所。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、Windows WMI オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンと Visual c# バージョンにアクセスする、 **System.Management** .NET Framework で提供されているオブジェクト。 これらのバージョンのどちらも最終的には、次の操作を実行する BizTalk Server WMI プロバイダーにアクセスします。  
  
-   一連のクエリが構成されている受信場所または特定の受信場所、名前を指定します。  
  
-   取得し、それぞれの詳細を表示の目的の場所を受信します。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 サンプルは、次の SDK の場所に配置されます。  
  
- VBScript バージョン:\<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\VBScript\ の受信  
  
- VisualC#バージョン。\<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\CSharp\ の受信  
  
  次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー。<br /><br /> EnumRecLocs.vbs|受信場所を構成済みのすべての詳細を取得する VBScript ファイル。|  
|\CSharp フォルダー。<br /><br /> App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs|プロジェクト、ソリューション、および Visual c# コマンド ラインを取得するアプリケーションの詳細については、構成済みのすべてを構築するためのソース ファイルは、受信場所、または特定の受信場所。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 受信場所の列挙サンプルの VBScript バージョンは、ビルドまたは初期化する必要はありませんは、1 つ Visual Basic スクリプト ファイルで構成されます。  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a>受信場所の列挙サンプルの Visual c# バージョンをビルドするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション ファイル BTSampleEnumerateRLs.sln を開きます。  
  
2. **ビルド** メニューのをクリックして**ソリューションのビルド**します。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a>受信場所の列挙サンプルを実行するには  
  
1.  コマンド ウィンドウでは、それぞれの VBScript バージョンと、このサンプルの Visual c# バージョンを実行することかどうかに応じて、次のフォルダーのいずれかに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\VBScript\ の受信  
  
     \<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\CSharp\bin\Debug\ の受信  
  
2.  EnumRecLocs.vbs cscript プログラムを使用してファイルを実行するか、それぞれの VBScript バージョンと、このサンプルの Visual c# バージョンを実行することかどうかに応じて EnumRl.exe、ファイルを実行します。 Visual c# のバージョンには、次の 2 つのコマンドライン引数のいずれかを渡します。  
  
    -   **\<ReceiveLocationName\>.** 詳細が表示されます、受信場所の名前。 受信場所の名前にスペースが含まれている場合は、名前を引用符で囲みます。  
  
    -   **/?.** ヘルプを表示します。  
  
         例 (VBScript)。  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         -または-(Visual c#)。  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         -または-(Visual c#)。  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  このサンプルの VBScript バージョンは、任意のコマンド ライン パラメーターを受け入れませんあり、したがってのみを取得できると、表示の詳細については、構成済みのすべての受信場所。  
  
## <a name="comments"></a>コメント  
 すべてのタスクで実行できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジュアルを使用して、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することもC#にアクセスする、 **System.Management**オブジェクト.NET Framework によって提供されます。  
  
 スクリプト ファイル EnumRecLocs.vbs および Visual c# ソース ファイル EnumRLs.cs 詳細なコメントが実行する操作についての説明が含まれます。 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)