---
title: オーケストレーション (BizTalk Server サンプル) を停止 |Microsoft ドキュメント
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
ms.openlocfilehash: 8b0c88bdeb85b8ad493b85d2569061c35bd516e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973896"
---
# <a name="stop-orchestration-biztalk-server-sample"></a>オーケストレーション (BizTalk Server サンプル) を停止します。
オーケストレーションの停止のサンプルは、BizTalk Server オーケストレーションの停止方法および参加解除方法 (オプション) を示しています。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。  
  
-   オーケストレーション名とアセンブリ名を受け取ると、展開された特定の BizTalk Server オーケストレーションに対するクエリを実行します。  
  
-   そのオーケストレーションを停止します。  
  
-   オーケストレーションを参加解除します (オプション)。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプル ファイルは、次の SDK の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\WMI\Stop Orchestration\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> StopOrch.vbs|停止および参加解除 (オプション) の対象となるオーケストレーションを指定するパラメータを取る VBScript ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 オーケストレーションの停止のサンプルは、構築または初期化が不要な 1 つの VBScript ファイルで構成されます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Stop Orchestration\VBScript\  
  
2.  cscript プログラムを使用し、次のコマンド ライン引数 (3 番目はオプション) を渡して、ファイル StopOrch.vbs を実行します。  
  
    -   **\<** ***OrchestrationName* \>です。** 停止および参加解除 (オプション) の対象となる BizTalk Server オーケストレーションの名前。  
  
    -   **\<** ***AssemblyName* \>です。** 特定のオーケストレーションが展開された BizTalk アセンブリの名前。 アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。  
  
    -   **参加を解除します。** オプションの文字列で、特定のオーケストレーションを停止および参加解除する必要があることを示します。  
  
         例:  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         - または -  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して実行することもできます。  
  
 スクリプト ファイル StopOrch.vbs には、実行する操作について説明する詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)