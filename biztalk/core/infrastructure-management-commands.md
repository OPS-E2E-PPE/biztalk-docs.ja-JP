---
title: "インフラストラクチャ管理コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c82dc5cb65156af86e66abfeffef206f18add5cb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="infrastructure-management-commands"></a>インフラストラクチャ管理コマンド
BAM 管理 (BM) ユーティリティ構成コマンドを使用すると、BAM の構成を取得および更新できます。  
  
-   get-config: BAM 構成ファイルを取得します。  
  
-   更新設定: BAM 構成を更新します。  
  
-   get 変更: BAM インフラストラクチャに変更を一覧表示します。  
  
-   get defxml: BAM プライマリ インポート データベース内のすべての成果物を含むファイルを取得します。  
  
> [!NOTE]
>  含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。 Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。 このスイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-config-command"></a>get-config コマンド  
 **使用方法**  
  
 **bm.exe get config ファイル名:\<出力ファイル\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ファイル名:\<出力ファイル\>|構成ファイルの保存場所のパスおよび名前です。|  
|サーバー:\<サーバー\>|省略可能: 構成の取得元のサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: 構成の取得元のデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 BAM 構成 XML を取得し、それを指定されたファイルに保存します。 **Get-config**コマンドでは、既存のファイルは上書きされません。  
  
 **使用例**  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a>update-config コマンド  
 **使用方法**  
  
 **bm.exe 更新 config ファイル名:\<構成ファイル\>**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ファイル名:\<構成ファイル\>|BAM インフラストラクチャの更新に使用する構成ファイルのパスおよび名前です。|  
  
 BAM 構成 XML ファイルに格納された情報で、ローカル コンピューターの構成を更新します。 追加できるのは、現在の構成にまだ存在しないサーバーおよびデータベースの名前だけです。 動的インフラストラクチャが既に展開されているサーバーまたはデータベースの名前を変更した場合、bm.exe からエラーが報告されます。  
  
 ファイルで配信された警告のファイルの格納場所を変更した場合、 SQL Notifications Services を再起動する必要があります。 NS サービスを再起動しなかった場合、警告は元のファイルの格納場所に配信され続けます。  
  
 ファイルの格納場所は、BAM 構成ファイルの次の行に修正を加えることによって変更します。  
  
 \<プロパティ名 ="FileDropUNC"\>\\\\< コンピューター名\>\alerts\</Property\>  
  
 参照を更新する適切な手順については、次を参照してください。[をバックアップおよび復元する BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)です。  
  
> [!IMPORTANT]
>  既に BAM 警告が構成されているとき、警告セクションを含まない BAM 構成ファイルを使って update-database コマンドを実行すると、今後、警告が生成されないよう、bm.exe により構成が上書きされます。  
  
 **使用例**  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a>get-changes コマンド  
 **使用方法**  
  
 **bm.exe get 変更 [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|サーバー:\<サーバー\>|省略可能: BAM プライマリ インポート データベースが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: 名前が指定されていない場合、bm.exe は BamPrimaryImport の既定の名前を使用します。|  
  
 BAM プライマリ インポート データベースに対して適用された変更一覧を取得します。 このコマンドを使用して、BAM インフラストラクチャに対する変更を監査できます。 このコマンドで返される情報は次のとおりです。  
  
 変更に使用されたコマンドの種類と、変更に使用されたファイル  
  
 変更を適用したユーザー  
  
 変更されたアクティビティ  
  
 変更されたビュー  
  
 **使用例**  
  
```  
bm.exe get-changes  
```  
  
 コマンドの出力  
  
 \#1: c:\bam\ordermanagement.xml の展開  
  
 By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).  
  
 アクティビティ: [ordermgmt]  
  
 ビュー: SalesManager  
  
## <a name="get-defxml-command"></a>get-defxml コマンド  
 **使用方法**  
  
 **bm.exe get defxml-filename:\<出力ファイル\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ファイル名:\<出力ファイル\>|定義の保存先ファイルのパスおよび名前です。|  
|サーバー:\<サーバー\>|省略可能: 定義の取得元のサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: 定義の取得元のデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 BAM プライマリ インポート データベースからすべてのアイテムを取得し、それらを XML ファイルとして保存します。 既存のファイルは上書きされません。  
  
 **使用例**  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)