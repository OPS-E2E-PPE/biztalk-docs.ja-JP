---
title: ListApp コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5329dd55-4ce7-46d2-8983-90ac33725055
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e397fe9ad768ffa367c6699ec2f3abb4006e4a26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328725"
---
# <a name="listapp-command"></a>ListApp コマンド
すべてのローカル一意識別子 (LUID) と各成果物の種類の BizTalk アプリケーション内のリソース アイテムの一覧をコンソールに出力します。 リソース アイテムが 1 つを使用して BizTalk アプリケーションに追加できる、 [AddResource コマンド](../core/addresource-command.md)アセンブリ、スクリプト、ファイル、ポリシー、COM コンポーネント、仮想ディレクトリ、BAM アイテム、または証明書など。 これらのリソース アイテムは、BizTalk Server 管理コンソールの [リソース] ノードにも表示します。  
  
 このコマンドに ResourceSpec パラメーターを指定する場合は、同じ情報が .xml ファイルに書き込まれます。 この .xml ファイルを使用することができます、 **ExportApp** 」の説明に従って、.msi ファイルに、アプリケーション内のアイテムのサブセットをエクスポートするコマンドを[ExportApp コマンド](../core/exportapp-command.md)します。  
  
 仮想ディレクトリは、このコマンドで"localhost"Web サーバーのホスト名に置き換えます ExportApp コマンドで ResourceSpec パラメーターによって生成されたファイルを使用する場合は、ファイルをホスト名に"localhost"を置換し、Web サーバーがリモート コンピューターに存在する場合、ポート番号を手動で編集します。 この作業を行わないと、仮想ディレクトリとその内容が、アプリケーションの .msi ファイルに追加されません。  
  
 例: http://MyWebServer:80/MyVirtualDirectory します。  
  
## <a name="usage"></a>使用方法  
 **BTSTask の ListApp** [**/applicationname は:**<em>値</em>] [**/ResourceSpec:**<em>値</em>] [**/Server:**<em>値</em>] [**/database:**<em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|いいえ|アイテムを一覧表示する BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。  このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。|  
|**/ResourceSpec** (または **/R**、「解説」を参照してください)|いいえ|このコマンドで生成する .xml ファイルの完全パス。 このファイルは、対応する LUID およびそれぞれの型と共に、アプリケーションのアイテムを一覧表示されます。 例:C:\Artifacts\MyArtifacts.xml。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。 既に同じパスとファイル名を持つファイルが存在する場合は上書きされます。|  
|**/サーバー** (または **/S**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/D**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask ListApp /ApplicationName:MyApplication /ResourceSpec:C:\Artifacts\MyArtifacts.xml**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)