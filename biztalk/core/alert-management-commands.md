---
title: "アラートの管理コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f419e7a0019287383080c319961b8a3831d27bb4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="alert-management-commands"></a>警告管理コマンド
BAM 管理ユーティリティの警告管理コマンドを使用すると、展開済みの警告を操作することができます。  
  
-   get アラート: 展開済みの警告の一覧を取得します。  
  
-   削除するアラート: 警告を削除します。  
  
-   有効にするアラート: 警告ビューを有効にします。  
  
-   無効にするアラート: ビューの警告を無効にします。  
  
> [!NOTE]
>  含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。 Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。 このスイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-alerts-command"></a>get-alerts コマンド  
 **使用方法**  
  
 **bm.exe get アラート [-ビュー:\<ビュー名\>] [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|警告の一覧を取得するビューの名前です。|  
|サーバー:\<サーバー\>|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 コマンドを実行するコンピューターで定義されている警告を一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a>remove-alerts コマンド  
 **使用方法**  
  
 **bm.exe 削除アラートの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|警告を削除するビューの名前です。|  
|サーバー:\<サーバー\>|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたビューから、すべての警告を削除します。  
  
 **使用例**  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a>enable-alerts コマンド  
 **使用方法**  
  
 **bm.exe 有効にするアラートの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|警告を有効にするビューの名前です。|  
|サーバー:\<サーバー\>|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたビューの警告を有効にします。  
  
 **使用例**  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a>disable-alerts コマンド  
 **使用方法**  
  
 **bm.exe 無効にするアラートの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|警告を無効にするビューの名前です。|  
|サーバー:\<サーバー\>|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定されたビューの警告を無効にします。  
  
 **使用例**  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)