---
title: "アクティビティ管理コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18caccaf5207b5a63d0272c5d9e0277270c3e04c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="activity-management-commands"></a>アクティビティ管理コマンド
BAM 管理ユーティリティのアクティビティ管理コマンドを使用すると、展開済みアクティビティを操作できます。  
  
-   get アクティビティ: 展開済みアクティビティの一覧を取得します。  
  
-   削除アクティビティ: アクティビティを削除します。  
  
-   get activitywindow: アクティビティの期間を取得します。  
  
-   セット activitywindow: アクティビティのアクティビティの期間を設定します。  
  
-   get index: インデックスの一覧を取得します。  
  
-   インデックスの作成: 新しいインデックスを作成します。  
  
-   delete インデックス: インデックスを削除します。  
  
-   get アーカイブ: アーカイブ済みアクティビティの動作を取得します。  
  
-   セット アーカイブ: アーカイブ済みアクティビティの動作を設定します。  
  
> [!NOTE]
>  含めることで任意の BAM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。 Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。 このスイッチは、通常の BAM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-activities-command"></a>get-activities コマンド  
 **使用方法**  
  
 **bm.exe の取得活動 [-ビュー:\<ビュー名\>] [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|[名前]:\<アクティビティ名\>|削除するアクティビティの名前です。|  
|サーバー:\<サーバー\>|省略可能: アクティビティの一覧を取得するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティの一覧の取得元のデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 このコマンドを実行したコンピューターに展開されているアクティビティが一覧表示されます。  
  
 **使用例**  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a>remove-activity コマンド  
 **使用方法**  
  
 **bm.exe 削除アクティビティの名前:\<アクティビティ名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|[名前]:\<アクティビティ名\>|削除するアクティビティの名前です。|  
|サーバー:\<サーバー\>|省略可能: アクティビティを削除するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティを削除するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたアクティビティを BAM プライマリ インポート データベースから削除します。 そのアクティビティに依存するビューが存在する場合、コマンドの実行は失敗し、エラーが報告されます。 remove-view コマンドを使用して、アクティビティに依存するすべてのビューを削除してから、remove-activity コマンドを再度実行してください。  
  
 **使用例**  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a>get-activitywindow コマンド  
 **使用方法**  
  
 **bm.exe get activitywindow-アクティビティ:\<アクティビティ名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|.Activity の名前。|  
|サーバー:\<サーバー\>|省略可能: アクティビティが存在するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたアクティビティの期間を表示します。 このコマンドにより、期間の長さと、その期間の基準となる単位が返されます。  
  
 **使用例**  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a>set-activitywindow コマンド  
 **使用方法**  
  
 **bm.exe セット activitywindow-アクティビティ:\<アクティビティ名\>- TimeLength:\<整数\>-TimeUnit: 月 &#124; 日付 &#124;です。1 時間 &#124;です。分 [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|アクティビティの名前です。|  
|TimeLength:\<整数\>|アクティビティの期間です。|  
|TimeUnit:Month &#124; 日付 &#124;です。1 時間 &#124;です。1 分|期間の測定単位。|  
|サーバー:\<サーバー\>|省略可能: アクティビティが存在するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたアクティビティの期間を設定します。  
  
 **使用例**  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a>get-index コマンド  
 **使用方法**  
  
 **bm.exe get インデックス-アクティビティ:\<アクティビティ名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|アクティビティの名前です。|  
|サーバー:\<サーバー\>|省略可能: アクティビティが存在するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定のアクティビティについて作成されたすべてのインデックスを一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a>create-index コマンド  
 **使用方法**  
  
 **bm.exe インデックスの作成-indexname:\<インデックス名\>-アクティビティ:\<アクティビティ名\>-チェックポイント:\<checkpoint1\>[、\<チェックポイント 2\>...][-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|IndexName:\<インデックス名\>|新しいインデックスの名前です。|  
|アクティビティ:\<アクティビティ名\>|インデックスが作成されるアクティビティの名前。|  
|チェックポイント:\<checkpoint1\>[、\<チェックポイント 2\>...]|インデックスの一連のチェックポイントをコンマ区切りで指定します。|  
|サーバー:\<サーバー\>|省略可能: アクティビティが存在するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたチェックポイントを使用して、指定されたアクティビティのインデックスを作成します。  
  
 **使用例**  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a>delete-index コマンド  
 **使用方法**  
  
 **bm.exe delete インデックス-indexname:\<インデックス名\>-アクティビティ:\<アクティビティ名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|IndexName:\<インデックス名\>|削除するインデックスの名前。|  
|アクティビティ:\<アクティビティ名\>|インデックスの削除対象アクティビティの名前です。|  
|サーバー:\<サーバー\>|省略可能: アクティビティが存在するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたアクティビティから、特定の名前を指定してインデックスを削除します。  
  
 **使用例**  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a>set-archive コマンド  
 **使用方法**  
  
 **bm.exe get アーカイブ-アクティビティ:\<アクティビティ\>[-サーバー:\<サーバー\>] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|動作の表示対象アクティビティの名前です。|  
|サーバー:\<サーバー\>|省略可能: アクティビティが存在するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定したアクティビティのアーカイブ パッケージの動作 (アクティビティ データのアーカイブまたは削除) を取得します。  
  
 **使用例**  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a>set-archive コマンド  
 **使用方法**  
  
 **bm.exe セット アーカイブ - アクティビティ:\<アクティビティ\>- ShouldArchive: True [-サーバー:\<サーバー\>] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|動作の表示対象アクティビティの名前です。|  
|ShouldArchive: True|True に設定すると、アクティビティはアーカイブ済みデータベースに移動されます。 False に設定すると、アーカイブが削除されます。|  
|サーバー:\<サーバー\>|省略可能: アクティビティが存在するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定したアクティビティのデータがアーカイブ済みデータベースに移動されるよう、アーカイブ パッケージの動作を設定します。 既定では、展開済みの新しいアクティビティに対してこの動作が設定されます。  
  
 **使用例**  
  
 BAM アクティビティ データを削除するには、次のコマンドを実行します。  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 BAM アクティビティ データを BAMArchive データベースに移動するには、次のコマンドを実行します。  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)