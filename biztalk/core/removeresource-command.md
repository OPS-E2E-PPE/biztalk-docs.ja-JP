---
title: "RemoveResource コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e2c6046-43d4-4ac1-a1b1-3795b4e44038
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d091c46ea25cbb2489264316239b6763d841a47e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="removeresource-command"></a>RemoveResource コマンド
BizTalk 管理データベースからアイテムを削除します。 アイテムが、グローバル アセンブリ キャッシュ (GAC)、ファイル システム、証明書ストア、インターネット インフォメーション サービス、または Windows レジストリに存在していた場合、このコマンドを実行しても、これらの場所からは削除されません。 BAM プライマリ インポート データベースの BAM 定義やルール エンジン データベースのポリシーは削除されません。 このコマンドを実行してバインド ファイルを削除した場合、バインド ファイルが削除されるのみで、バインドそのものは変更されません。  
  
 このコマンドでは、次の種類のアイテムを削除できます。  
  
-   .NET アセンブリ (System.BizTalk:Assembly)  
  
-   BAM 定義 (System.BizTalk:Bam)  
  
-   BizTalk アセンブリ (System.BizTalk:BizTalkAssembly)  
  
-   BizTalk バインド ファイル (System.BizTalk:BizTalkBinding)  
  
-   セキュリティ証明書 (System.BizTalk:Certificate)  
  
-   COM コンポーネント (System.BizTalk:Com)  
  
-   アドホック ファイル (System.BizTalk:File)  
  
-   処理後のスクリプト (System.BizTalk:PostProcessingScript)  
  
-   処理前のスクリプト (System.BizTalk:PreProcessingScript)  
  
-   ポリシーまたはルール (System.BizTalk:Rules)  
  
-   仮想ディレクトリ (System.BizTalk:WebDirectory)  
  
 次の場合、削除操作は失敗します。  
  
-   他のアセンブリによって参照されている BizTalk アセンブリを削除しようとした場合。  
  
-   送信ポートまたは受信ポートによって使用されているパイプラインを含む BizTalk アセンブリを削除しようとした場合。  
  
-   送信ポートが使用しているマップを含む BizTalk アセンブリを削除しようとした場合。  
  
-   削除しようとしている BizTalk アセンブリにオーケストレーションが含まれており、そのオーケストレーションが参加解除状態ではない、または、そのオーケストレーションに、中断されたインスタンスが存在する場合。  
  
## <a name="usage"></a>使用方法  
 **BTSTask RemoveResource/applicationname は:** *値* **/Luid:** *値*[**/Server:** *値*] [**/database:***値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|Description|  
|---------------|--------------|-----------------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|はい|削除するリソース アイテムが存在する BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/Luid** (または**/L**、「解説」を参照してください)|はい|アイテムのローカル一意識別子 (LUID)。 使用して、LUID を取得することができます、 [ListApp コマンド](../core/listapp-command.md)です。|  
|**/サーバー** (または**/S**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/D**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask RemoveResource applicationname: myapplication/Luid:"MyApp.Orchestrations、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 0123456789ABCDEF"**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [アプリケーションからアイテムを削除する方法](../core/how-to-remove-an-artifact-from-an-application.md)