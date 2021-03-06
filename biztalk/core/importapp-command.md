---
title: ImportApp コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8ee5a78-1e8f-4290-b70a-36f2f888a1d6
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fba2557e502420024403b1666946443ec99ca567
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382512"
---
# <a name="importapp-command"></a>ImportApp コマンド
.msi ファイルに格納されたアイテムを BizTalk アプリケーションにインポートします。 指定したアプリケーションが存在しない場合は、新しく作成されます。  
  
 アプリケーションをインポートするとき、特定の展開環境用にカスタマイズしたバインド ファイルがそのアプリケーションに追加されていれば、/Environment パラメーターで、アプリケーションの展開先環境を指定できます。 背景情報は、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。 バインド ファイルを追加する手順については、次を参照してください。 [AddResource コマンド。BizTalk バインド](../core/addresource-command-biztalk-binding.md)します。  
  
> [!NOTE]
>  インポート操作の所要時間が 3600 秒を超えた場合は、タイムアウトになります。 .msi ファイルをインポートするとき、操作がタイムアウトした場合は、アプリケーションを再度エクスポートし、エクスポートするアイテムのサブセットを選択して、アプリケーションのコンテンツを複数の .msi ファイルに分割する必要があります。 詳細については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。  
  
 インポートが失敗した場合、BTSTask はエラーの数を示す値を返します。 操作中に実行されたほとんどのアクションはロールバックされます。ただし、次のアクションはロールバックされません。  
  
- カスタム スクリプトによって実行されたアクションはロールバックされません。 Delete 環境変数を使用することにより、ロールバックに対応したスクリプトを作成することもできます。  
  
- グローバル アセンブリ キャッシュ (GAC) にインストールされたアセンブリは削除されません。  
  
- Windows レジストリに登録されたエントリは削除されません。  
  
  インポートが正常に完了した場合、BTSTask は "0" を返します。  
  
## <a name="usage"></a>使用方法  
 **BTSTask の ImportApp/Package:** *値*[**/Environment:**<em>値</em>] [**/applicationname は:** <em>値</em>] **[/overwrite]** [**/Server:**<em>値</em>] [**/database:**<em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/パッケージ**(または **/P**、「解説」を参照してください)|はい|.msi ファイルの完全パス。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 例:"C:\My MSI Files\MyApplication.msi"|  
|**/環境**(または **/E**、「解説」を参照してください)|いいえ|バインド ファイルの適用対象の展開環境 (Test など)。 これは、バインド ファイルをアプリケーションに追加するときに、対象の展開環境として指定した値です。 指定しなかった場合、環境の指定されていないすべてのバインドが適用されます。|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|いいえ|.msi ファイル内のアイテムをインポートする BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 指定しなかった場合、既定のアプリケーションが使用されます。 指定したアプリケーションが存在しない場合は、アプリケーションが新しく作成されます。|  
|**/上書き**(または **/O**、「解説」を参照してください)|いいえ|.msi ファイル内のアイテムと、アプリケーション内のアイテムとが、同じローカル一意識別子 (LUID) を持つ場合に、アプリケーション内のアイテムを上書きするためのオプション。 使用して、アプリケーションでアイテムの Luid を表示することができます、 [ListApp コマンド](../core/listapp-command.md)します。 このオプションを省略した場合、.msi ファイル内のアイテムと同じ LUID を持つアイテムがアプリケーションに存在すると、インポートは失敗します。|  
|**/サーバー** (または **/S**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/D**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask ImportApp /Package:C:\MSI\MyApplication.msi /Environment:Test /ApplicationName:MyApplication /Overwrite**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)