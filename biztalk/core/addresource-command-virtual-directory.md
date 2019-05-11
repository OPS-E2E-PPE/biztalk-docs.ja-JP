---
title: AddResource コマンド:仮想ディレクトリ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 446be3b3-31da-4f03-81b5-3a75c8da6558
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de084d8ca925985373da2cb2606f6d016a20cdba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360286"
---
# <a name="addresource-command-virtual-directory"></a>AddResource コマンド:[仮想ディレクトリ]
使用する BizTalk アプリケーションには、Web サイトまたは Web サービス用の仮想ディレクトリを追加するには**AddResource**コマンドを指定**System.BizTalk:WebDirectory**型パラメーター。 このコマンドを実行すると、仮想ディレクトリが BizTalk 管理データベースに追加します。 仮想ディレクトリは、BizTalk Server 管理コンソールで、追加したアプリケーションのリソース フォルダーにも表示されます。 使用するとさらに、仮想ディレクトリが一覧表示、 [ListApp コマンド](../core/listapp-command.md)します。  
  
> [!IMPORTANT]
>  Https が含まれる URL を使用して仮想ディレクトリを追加する場合は、https ではなく、指定した URL に http を使用する必要があります。 Https を使用する場合は、仮想ディレクトリを追加する操作は失敗します。 を URL に http で追加する場合でも、インターネット インフォメーション サービス メタベースに URL の https 設定が有効、になり、仮想ディレクトリが正常に機能します。  
  
> [!NOTE]
>  64 ビット版は、Web サービスから仮想ディレクトリを追加して、32 ビット コンピューター上の仮想ディレクトリを含むアプリケーションをインストールしようとした、仮想ディレクトリはインストールされません。 64 ビット コンピューターにのみインストールされます。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [/**ApplicationName:**<em>値</em>] **/Type:System.BizTalk:WebDirectory****[/overwrite]****/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Server:** <em>値</em>] [**/database:**<em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|                   パラメーター                   | 必須 |                                                                                                                                                                                                                                                         値                                                                                                                                                                                                                                                          |
|-----------------------------------------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **/ApplicationName** (または **/A**、「解説」を参照してください) |    いいえ    |                                                                                                                                仮想ディレクトリを追加する BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。                                                                                                                                 |
|      **/入力**(または **/T**、「解説」を参照してください)       |   はい    |                                                                                                                                                                                                                          **System.BizTalk:WebDirectory** (この値小文字は区別されません)。                                                                                                                                                                                                                           |
|    **/上書き**(または **/O**、「解説」を参照してください)    |    いいえ    |                                                                                                                                               既存の仮想ディレクトリを更新するオプション。 指定されていない場合、追加される仮想ディレクトリ、AddResource 操作は失敗と同じ名前を持つアプリケーションで仮想ディレクトリが既に存在します。                                                                                                                                                |
|     **/Source** (または **/S**、「解説」を参照してください)      |   はい    |                                                                                                                                                                                                 ソース仮想ディレクトリの完全な URI です。<br /><br /> 例 :<br /><br /> http://MyHost:80/MyPath/MyVirtualDirectory                                                                                                                                                                                                 |
|  **/変換先**(または **/De**、「解説」を参照してください)   |    いいえ    |                                                                                                                                                    .Msi ファイルから、アプリケーションがインストールされている場合、仮想ディレクトリに割り当てる URI。 このパラメーターが指定されていない場合、ソース パラメーターの値として使用されます localhost のホスト。                                                                                                                                                    |
|     **/サーバー** (または **/S**、「解説」を参照してください)      |    いいえ    | BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。 |
|    **/データベース**(または **/Da**、「解説」を参照してください)    |    いいえ    |                                                                                                                                                                                     BizTalk 管理データベースの名前。 指定されていない場合は、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。                                                                                                                                                                                     |
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:WebDirectory/overwrite/Source:<http://Host1:90/MyVirtualDirectory> /Destination:<http://Host2:90/MyVirtualDirectory> /Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [.NET アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-net-assembly-to-an-application.md)