---
title: "管理コマンドの表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52f25ee3-9bb3-4682-a9ff-cac8c25f58c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0a641c6d461d02f8db3e0fb0112321e0657e44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="view-management-commands"></a>ビュー管理コマンド
BAM 管理ユーティリティのビュー管理コマンドを使用すると、展開済みのビューを操作できます。  
  
-   get ビュー: すべての展開されたビューを一覧表示します。  
  
-   削除ビュー: 展開されたビューを削除します。  
  
-   get rtawindow: ビューの期間を取得します。  
  
-   セット rtawindow: ビューの期間を設定します。  
  
> [!NOTE]
>  含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で & #124 オフ**パラメーター スイッチ。 Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。 このスイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-views-command"></a>get-views コマンド  
 **使用方法**  
  
 **bm.exe get ビュー [-アクティビティ:\<アクティビティ名 >] [-サーバー:\<サーバー >] [-データベース:\<データベース >]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名 >|ビューを一覧表示するアクティビティの名前です。|  
|サーバー:\<サーバー >|省略可能: ビューの一覧を取得するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース >|省略可能: ビューの一覧の取得元のデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 コマンドを実行するコンピューターに展開されているビューを一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a>remove-view コマンド  
 **使用方法**  
  
 **bm.exe 削除ビューの名前:\<ビュー名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|[名前]:\<ビュー名 >|削除するビューの名前です。|  
|サーバー:\<サーバー >|省略可能: ビューを削除するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース >|省略可能: ビューを削除するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたビューを BAM プライマリ インポート データベースから削除します。 そのビューに依存する警告が存在する場合、これらの警告も同時に削除されます。  
  
 **使用例**  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a>get-rtawindow コマンド  
 **使用方法**  
  
 **bm.exe get rtawindow-ビュー:\<ビュー名 >-アクティビティ:\<アクティビティ名 > -Rta:\<RTA 名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名 >|ビューの名前です。|  
|アクティビティ:\<アクティビティ名 >|アクティビティ名。|  
|Rta:\<RTA 名 >|リアルタイム集計の名前です。|  
|サーバー:\<サーバー >|省略可能: アクティビティが存在するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース >|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたリアルタイム集計の期間を表示します。 このコマンドにより、期間の長さと、その期間の基準となる単位が返されます。  
  
 **使用例**  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a>set-rtawindow コマンド  
 **使用方法**  
  
 **bm.exe セット rtawindow-ビュー:\<ビュー名 >-アクティビティ:\<アクティビティ名 >-名前:\<RTA 名 > - TimeLength:\<整数の番号 >-TimeUnit:Day & #124 です。1 時間 & #124 です。分 [-サーバー:\<サーバー >] [-データベース:\<データベース >]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名 >|ビューの名前です。|  
|アクティビティ:\<アクティビティ名 >|アクティビティ名。|  
|[名前]:\<RTA 名 >|リアルタイム集計の名前です。|  
|TimeLength:\<整数 >|リアルタイム集計の期間です。|  
|TimeUnit:Month &#124; 日付 & #124 です。1 時間 & #124 です。1 分|期間の単位です。|  
|サーバー:\<サーバー >|省略可能: アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行しているコンピューターと同じドメインにする必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース >|省略可能: アクティビティが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたリアルタイム集計の期間を設定します。  
  
 **使用例**  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)