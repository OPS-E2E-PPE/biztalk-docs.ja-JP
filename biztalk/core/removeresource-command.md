---
title: RemoveResource コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e2c6046-43d4-4ac1-a1b1-3795b4e44038
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc7b5e6f5d254624f295aef16761d074379f3ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397919"
---
# <a name="removeresource-command"></a>RemoveResource コマンド
(削除)、BizTalk 管理データベースからのアイテム。 このコマンドの実行は削除されません、成果物、グローバル アセンブリ キャッシュ (GAC)、ファイル システム、証明書ストア、インターネット インフォメーション サービス、または、Windows レジストリからこれらの場所のいずれかに存在する場合。 BAM 定義は、BAM プライマリ インポート データベースから削除されませんしても、ポリシー、ルール エンジン データベースからです。 バインド ファイルを削除するには、このコマンドを実行すると、バインドされても変更されません: バインド ファイルのみが削除されます。  
  
 このコマンドを使用して、次の成果物の種類を削除することができます。  
  
- .NET アセンブリ (System.BizTalk:Assembly)  
  
- BAM 定義 (System.BizTalk:Bam)  
  
- BizTalk アセンブリ (system.biztalk:biztalkassembly)  
  
- BizTalk バインド ファイル (System.BizTalk:BizTalkBinding)  
  
- セキュリティ証明書 (System.BizTalk:Certificate)  
  
- COM コンポーネント (System.BizTalk:Com)  
  
- アドホック ファイル (System.BizTalk:File)  
  
- 処理後のスクリプト (System.BizTalk:PostProcessingScript)  
  
- 処理前のスクリプト (System.BizTalk:PreProcessingScript)  
  
- ポリシーまたはルール (System.BizTalk:Rules)  
  
- 仮想ディレクトリ (System.BizTalk:WebDirectory)  
  
  次の場合、削除操作は失敗します。  
  
- 別のアセンブリが参照を持っている BizTalk アセンブリを削除しようとするとします。  
  
- ポートまたは受信ポート、送信で使用されるパイプラインを含む BizTalk アセンブリを削除しようとするとします。  
  
- 送信ポートで使用されるマップを含む BizTalk アセンブリを削除しようとするとします。  
  
- 参加解除状態でないか、中断されたインスタンスを持つオーケストレーションを含む BizTalk アセンブリを削除しようとするとします。  
  
## <a name="usage"></a>使用方法  
 **BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|説明|  
|---------------|--------------|-----------------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|はい|削除するリソース アイテムが含まれる BizTalk アプリケーションの名前です。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/Luid** (または **/L**、「解説」を参照してください)|はい|成果物のローカルで一意の識別子 (LUID)。 LUID を取得するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。|  
|**/サーバー** (または **/S**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/D**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [アプリケーションからアイテムを削除する方法](../core/how-to-remove-an-artifact-from-an-application.md)