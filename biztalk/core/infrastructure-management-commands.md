---
title: インフラストラクチャ管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a75743ae6f6b65bcab0afa42dd5536e8bfbf1c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382192"
---
# <a name="infrastructure-management-commands"></a>インフラストラクチャ管理コマンド
BAM 管理 (BM) ユーティリティ構成コマンドを許可すると、取得、および BAM 構成を更新します。  
  
-   get-config:BAM 構成ファイルを取得します。  
  
-   update-config:BAM 構成を更新します。  
  
-   get 変更:BAM インフラストラクチャの変更を一覧表示します。  
  
-   get defxml:BAM プライマリ インポート データベース内のすべての成果物を含むファイルを取得します。  
  
> [!NOTE]
>  含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。 トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。 スイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-config-command"></a>get-config コマンド  
 **使用方法**  
  
 **bm.exe get-config -FileName:\<output file\> [ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ファイル名:\<出力ファイル\>|パスと、構成ファイルの保存先となる名前。|  
|サーバー:\<サーバー\>|省略可能:構成の取得元のサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:構成の取得元のデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 BAM 構成 XML を取得し、指定したファイルに保存します。 **Config の取得**コマンドでは、既存のファイルは上書きされません。  
  
 **使用例**  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a>update-config コマンド  
 **使用方法**  
  
 **bm.exe update-config -FileName:\<config file\>**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ファイル名:\<構成ファイル\>|パスと、BAM インフラストラクチャを更新する構成ファイルの名前。|  
  
 BAM 構成 XML を含むファイルからローカル コンピューター上の構成を更新します。 現在の構成では、サーバーおよび存在しないデータベース名を追加できます。 サーバーまたはデータベース名にデプロイされている動的インフラストラクチャが既に存在する変更は失敗し、bm.exe エラーが報告されます。  
  
 ファイルで配信された警告のファイルの格納場所を変更した場合、 SQL Notifications Services を再起動する必要があります。 NS サービスを再起動しなかった場合、警告は元のファイルの格納場所に配信され続けます。  
  
 BAM 構成ファイルの次の行を変更することで、ファイルの格納場所が変更されます。  
  
 \<プロパティ名 ="FileDropUNC"\>\\\\< コンピューター名\>\alerts\</Property\>  
  
 参照を更新する適切な手順については、次を参照してください。[をバックアップおよび復元する BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)します。  
  
> [!IMPORTANT]
>  Update-database コマンドを実行すると、[アラート] セクションを含まない BAM 構成ファイルを使用して、BAM 警告を構成済みである場合は、アラートが機能しなくなりますように bm.exe は構成を上書きします。  
  
 **使用例**  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a>get-changes コマンド  
 **使用方法**  
  
 **bm.exe の get 変更 [-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|サーバー:\<サーバー\>|省略可能:BAM プライマリ インポート データベースが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 BAM プライマリ インポート データベースに適用された変更の一覧を取得します。 このコマンドを使用して、BAM インフラストラクチャの変更を監査することができます。 次の情報が返されます。  
  
 変更と変更が適用された元のファイルのコマンドの種類。  
  
 変更を適用したユーザー。  
  
 変更されたアクティビティ。  
  
 ビューが変更されました。  
  
 **使用例**  
  
```  
bm.exe get-changes  
```  
  
 コマンドの出力  
  
 \#1:Deploy c:\bam\ordermanagement.xml  
  
 12/30/2005 には、ドメイン \ ユーザーによって 8時 17分: 08 PM (v3.5.1536.0)。  
  
 アクティビティ:[Ordermgmt]  
  
 Views:SalesManager  
  
## <a name="get-defxml-command"></a>get-defxml コマンド  
 **使用方法**  
  
 **bm.exe get-defxml -FileName:\<output file\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ファイル名:\<出力ファイル\>|パスと、定義の保存先となるファイルの名前。|  
|サーバー:\<サーバー\>|省略可能:定義の取得元のサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:定義の取得元のデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 BAM プライマリ インポート データベースからのすべての成果物を取得しに XML ファイルとして保存します。 コマンドでは、既存のファイルは上書きされません。  
  
 **使用例**  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)