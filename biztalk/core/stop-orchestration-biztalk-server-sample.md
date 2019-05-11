---
title: オーケストレーションの停止 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, stopping
ms.assetid: 83be44e9-819d-4ac5-8b75-84c23e6b5ba2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5f6294442311f2644f6f0bc7efd2261af7712c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244162"
---
# <a name="stop-orchestration-biztalk-server-sample"></a>オーケストレーションの停止 (BizTalk Server サンプル)
オーケストレーションの停止サンプルでは、BizTalk Server オーケストレーションを停止し、必要に応じて参加を解除します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示します。  
  
-   オーケストレーション名とアセンブリ名を指定するには、特定のクエリには、BizTalk Server オーケストレーションが展開されています。  
  
-   そのオーケストレーションを停止します。  
  
-   (省略可能)、そのオーケストレーションを参加解除します。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 サンプル ファイルは、次の SDK の場所に配置されます。  
  
 \<*パスのサンプル*\>\Admin\WMI\Stop Orchestration\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー。<br /><br /> StopOrch.vbs|オーケストレーションが停止し、必要に応じて、参加解除の対象を指定するパラメータを受け取る VBScript ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 オーケストレーションの停止のサンプルは、ビルドまたは初期化する必要はありませんが、1 つの VBScript ファイルで構成されます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Stop Orchestration\VBScript\  
  
2.  ファイル StopOrch.vbs cscript プログラムを使用して、3 つ目は省略可能ですが、次のコマンドライン引数を渡すことを実行します。  
  
    -   **\<** ***OrchestrationName* \>.** BizTalk Server オーケストレーションを停止して、必要に応じて、参加解除の対象の名前。  
  
    -   **\<** ***AssemblyName* \>.** 特定のオーケストレーションが展開されている BizTalk アセンブリの名前。 アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。  
  
    -   **参加を解除します。** 省略可能なリテラル文字列、特定のオーケストレーションを停止および参加する必要があるように指定するために使用します。  
  
         以下に例を示します。  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         -または-  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル StopOrch.vbs には、詳細なコメントが、実行する操作についての説明が含まれています。 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)