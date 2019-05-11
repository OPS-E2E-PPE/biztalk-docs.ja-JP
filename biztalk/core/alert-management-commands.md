---
title: アラートの管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 651bc1d0df943df022cf597bb7292cb3143ad327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359302"
---
# <a name="alert-management-commands"></a>警告管理コマンド
BAM 管理ユーティリティの警告管理コマンドを使用すると、展開済みの警告を使用できます。  
  
-   get アラート:展開済みの警告の一覧を取得します。  
  
-   削除通知:警告を削除します。  
  
-   有効にするアラート:ビューの警告を有効にします。  
  
-   無効にするアラート:ビューの警告を無効にします。  
  
> [!NOTE]
>  含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。 トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。 スイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-alerts-command"></a>get-alerts コマンド  
 **使用方法**  
  
 **bm.exe の get アラート [-ビュー:\<ビュー名\>] [-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|アラートの一覧の取得元のビューの名前。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 コマンドを実行するコンピューターで定義された警告を一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a>remove-alerts コマンド  
 **使用方法**  
  
 **bm.exe 削除-アラートの表示:\<ビュー名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|アラートを削除するビューの名前。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 すべての警告を指定されたビューを削除します。  
  
 **使用例**  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a>enable-alerts コマンド  
 **使用方法**  
  
 **bm.exe の有効にするアラートの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|アラートを有効にするビューの名前。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定されたビューの警告を有効にします。  
  
 **使用例**  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a>disable-alerts コマンド  
 **使用方法**  
  
 **bm.exe の無効にするアラートの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|アラートを無効にするビューの名前。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定されたビューの警告を無効にします。  
  
 **使用例**  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)