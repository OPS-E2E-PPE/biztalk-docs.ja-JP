---
title: 管理コマンドの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f25ee3-9bb3-4682-a9ff-cac8c25f58c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbd91cf632b655fe3c2cb535f2ee4db3c889688d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243250"
---
# <a name="view-management-commands"></a>ビュー管理コマンド
BAM 管理ユーティリティのビュー管理コマンドを使用すると、展開されているビューを使用できます。  
  
-   get ビュー:展開されているすべてのビューを一覧表示します。  
  
-   削除ビュー:ビューが展開を削除します。  
  
-   get-rtawindow プロパティ:ビューの期間を取得します。  
  
-   セット-rtawindow プロパティ:ビューの期間を設定します。  
  
> [!NOTE]
>  含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。 トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。 スイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-views-command"></a>get-views コマンド  
 **使用方法**  
  
 **bm.exe の get ビュー [-アクティビティ:\<アクティビティ名\>] [-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|ビューを一覧表示するアクティビティの名前。|  
|サーバー:\<サーバー\>|省略可能:ビューの一覧の取得元のサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューの一覧の取得元のデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 コマンドを実行するコンピューターに展開されたビューを一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a>remove-view コマンド  
 **使用方法**  
  
 **bm.exe remove-view -Name:\<view name\> [ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|名前:\<ビュー名\>|削除するビューの名前。|  
|サーバー:\<サーバー\>|省略可能:元のビューを削除するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:元のビューを削除するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 BAM プライマリ インポート データベースから、指定されたビューを削除します。 ビューに依存するアラートがある場合は、同時に削除されます。  
  
 **使用例**  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a>get-rtawindow コマンド  
 **使用方法**  
  
 **bm.exe の get rtawindow プロパティの表示:\<ビュー名\>-アクティビティ:\<アクティビティ名\>Rta:\<RTA 名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|ビューの名前。|  
|アクティビティ:\<アクティビティ名\>|アクティビティ名。|  
|Rta:\<RTA 名\>|リアルタイム集計の名前。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定されたリアルタイム集計の期間を表示します。 コマンドは、期間と期間の測定単位の長さを返します。  
  
 **使用例**  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a>set-rtawindow コマンド  
 **使用方法**  
  
 **bm.exe セット-rtawindow プロパティのビュー:\<ビュー名\>-アクティビティ:\<アクティビティ名\>-名前:\<RTA 名\>- TimeLength:\<整数\>-TimeUnit: Day&#124;時間&#124;分 [-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|ビューの名前。|  
|アクティビティ:\<アクティビティ名\>|アクティビティ名。|  
|名前:\<RTA 名\>|リアルタイム集計の名前。|  
|TimeLength:\<整数\>|リアルタイム集計の期間です。|  
|TimeUnit:Month&#124;日&#124;時間&#124;分|期間の単位。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 Bm.exe の実行元となるマシンと同じドメインで、サーバーがあります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定されたリアルタイム集計の期間を設定します。  
  
 **使用例**  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)