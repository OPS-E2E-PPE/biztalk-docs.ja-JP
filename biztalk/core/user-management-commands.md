---
title: "ユーザー管理コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16527acda7432b2eea35f0c87bb9d89fff632430
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="user-management-commands"></a>ユーザー管理コマンド
BAM 管理ユーティリティの警告ユーザー管理コマンドを使用すると、ユーザーの取得、追加、および削除を行うことができます。  
  
-   get アカウント: すべてのユーザーと指定されたビューにアクセスできるグループの一覧を取得します。  
  
-   アカウントの追加: アクセス権を指定したユーザーまたはグループの指定されたビューを与えます。  
  
-   アカウントの削除: 指定されたビューからのアクセス権をユーザーまたはグループを削除します。  
  
> [!NOTE]
>  含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。 Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。 このスイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-accounts-command"></a>get-accounts コマンド  
 **使用方法**  
  
 **bm.exe get-アカウントの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|アカウントを一覧表示するビューの名前です。|  
|サーバー:\<サーバー\>|省略可能: アカウントを取得する対象のサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: アカウントを取得する対象のデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたビューにアクセスすることのできるすべてのユーザーおよびグループを一覧表示します。  
  
 **使用例**  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a>add-account コマンド  
 **使用方法**  
  
 **bm.exe アカウントの追加-accountname:\<アカウント名\>-ビュー:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|AccountName:<アカウント名|権限を付与するアカウントの名前です。|  
|ビュー:\<ビュー名\>|権限を付与するビューの名前です。|  
|サーバー:\<サーバー\>|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたユーザーまたはグループに対し、特定のビューに対するアクセス権を付与します。  
  
> [!IMPORTANT]
>  リアルタイム集計 (Rta) を使用している場合で追加されたユーザー**アカウントの追加**コマンドでは、SQL Server へのログオン権限が自動的に付与されません。 RTA を使用している場合は、RTA のビューを表示しなければならないすべてのユーザーを含む、Windows ユーザー グループの作成を検討してください。 BAM プライマリ インポート データベースをホストする SQL Server の明示的な SQL Server ログオン権限をそのグループに許可します。  
  
 **使用例**  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a>remove-account コマンド  
 **使用方法**  
  
 **bm.exe 削除アカウント-accountname:\<アカウント名\>-ビュー:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|AccountName:\<アカウント名\>|ビューに対するアクセス権を削除するアカウントの名前です。|  
|ビュー:\<ビュー名\>|権限を削除するビューの名前です。|  
|サーバー:\<サーバー\>|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたビューからユーザーまたはグループのアクセス権を削除します。 ビューからアカウントを削除すると、指定されたビューに対して定義されている警告から、対応するアカウントとそのすべてのメンバーが削除されます。 そのアカウントが、警告の唯一の所有者であった場合は、現在のユーザー (admin) が、その警告の新しい所有者になります。  
  
 **使用例**  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)