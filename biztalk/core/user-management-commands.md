---
title: ユーザー管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b79ff5a6bc94faab130de5d7d793612f2130d732
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399960"
---
# <a name="user-management-commands"></a>ユーザー管理コマンド
BAM 管理ユーティリティの警告のユーザー管理コマンドを使用すると、取得、追加、およびユーザーを削除できます。  
  
-   get アカウント:すべてのユーザーと指定されたビューにアクセスできるグループの一覧を取得します。  
  
-   追加のアカウント:指定されたビューを指定したユーザーまたはグループの権限のアクセス権を付与します。  
  
-   削除-アカウント:指定されたビューからユーザーまたはグループの権限にアクセスして削除します。  
  
> [!NOTE]
>  含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。 トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。 スイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-accounts-command"></a>get-accounts コマンド  
 **使用方法**  
  
 **bm.exe get-accounts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|アカウントを一覧表示する対象のビューの名前。|  
|サーバー:\<サーバー\>|省略可能:アカウントの取得元となるサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アカウントの取得元となるデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 すべてのユーザーと、指定されたビューにアクセスできるグループを一覧表示します。  
  
 **使用例**  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a>add-account コマンド  
 **使用方法**  
  
 **bm.exe add-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|AccountName: < アカウント名|権限を付与するアカウントの名前。|  
|ビュー:\<ビュー名\>|権限を付与するビューの名前。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定したユーザーまたはグループを指定されたビューのアクセス権を付与します。  
  
> [!IMPORTANT]
>  リアルタイム集計 (Rta) を使用している場合で追加されたユーザー**アカウントの追加**コマンドでは SQL Server へのログオン権限が自動的に付与されません。 RTA を使用している場合は、RTA のビューを表示しなければならないすべてのユーザーを含む、Windows ユーザー グループの作成を検討してください。 そのグループ BAM プライマリ インポート データベースをホストする SQL server で SQL Server ログオン権限を明示的に許可します。  
  
 **使用例**  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a>remove-account コマンド  
 **使用方法**  
  
 **bm.exe remove-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|AccountName:\<アカウント名\>|ビューに対する権限を削除するアカウントの名前。|  
|ビュー:\<ビュー名\>|権限を削除するビューの名前。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定されたビューからユーザーまたはグループの権限にアクセスして削除します。 ビューからアカウントを削除する、指定されたビューに定義された警告からそのアカウントとそのすべてのメンバーを削除します。 そのアカウントが、警告の唯一の所有者である場合は、現在のユーザー (管理者) は、アラートの新しい所有者になります。  
  
 **使用例**  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)