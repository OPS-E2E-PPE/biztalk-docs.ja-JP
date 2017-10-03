---
title: "管理 (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, examples
- utilities, SSOMANAGE
- examples, SSO
- SSOMANAGE command line utility
ms.assetid: f738e344-4d81-4557-b399-68b59c413245
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15a94bf916550d9a2eada9b8f354432b4c154ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manage-biztalk-server-sample"></a>管理 (BizTalk Server サンプル)
シングル サインオン (SSO) 管理のサンプルは、以下の種類の管理操作を実行するために、コマンド ライン ユーティリティ ssomanage.exe で使用できる .xml ファイルを構成する方法を示します。  
  
-   SSO システム レベルでのグローバル情報の更新  
  
-   関連アプリケーションを作成します。  
  
-   ユーザー マッピングの作成  
  
 エンタープライズ シングル サインオンに関する概念的な情報は、次を参照してください。[を使用して SSO](../core/using-sso.md)です。  
  
 関連アプリケーションやユーザー マッピングの作成など、SSO をプログラムで構成する方法を示すサンプルについては、次を参照してください。 [HTTPSSO (BizTalk Server サンプル)](../core/httpsso-biztalk-server-sample.md)です。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルには、上記の種類の操作のそれぞれに対する XSD とサンプル .xml ファイルのペアが含まれています。 サンプル .xml ファイルの値は有効ではありません。 各自の要件に合わせて値を変更する必要があります。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<サンプル パス >*\SSO\Manage\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|AffiliateApplication.xml、GlobalInfo.xml、UserMapping.xml|コマンド ライン ユーティリティ ssomanage.exe に引数を渡すサンプル .xml ファイルです。変更が必要です。|  
|AffiliateApplication.xsd、GlobalInfo.xsd、UserMapping.xsd|可能な要素と属性を完全に記述した、対応する .xml ファイルのスキーマ ファイルです。 これらのファイルを使用して、他のソースから受信した、対応する .xml ファイルを検証することができます。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 このサンプルは XSD (XML Schema Definition) 言語のファイルと .xml ファイルのみで構成され、後者は変更してコマンド ライン ユーティリティ ssomanage.exe に渡すため、このサンプルでビルドが必要なものはありません。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 このサンプルには、以下の 3 つの異なるモードでコマンド ライン ユーティリティ ssomanage.exe を実行するための、サンプルの .xml ファイルが含まれています。  
  
-   **SSO システム レベルでグローバル情報を更新します。** この種類の操作を実行するには、次の手順を実行します。  
  
    1.  各自の構成に合わせてファイル GlobalInfo.xml を編集します。  
  
    2.  以下のように、適切な引数を指定してコマンド ライン ユーティリティ ssomanage.exe を実行します。  
  
        ```  
        ssomanage –updatedb GlobalInfo.xml  
        ```  
  
     環境に合わせてファイル GlobalInfo.xml 内の値を編集します。 たとえば、SSO 管理者アカウントは有効な Windows アカウントである必要があります。 SSO 管理者アカウントと SSO 関連管理者アカウントの両方が、Windows のグローバル ドメイン グループ アカウントである必要があります。  
  
-   **関連アプリケーションを作成します。** この種類の操作を実行するには、次の手順を実行します。  
  
-   各自の構成要件に合わせてファイル AffiliateApplication.xml を編集します。  
  
    -   よう、適切な引数でコマンド ライン ユーティリティ ssomanage.exe を実行します。  
  
        ```  
        ssomanage –createapps AffiliateApplication.xml  
        ```  
  
     同時に複数の関連アプリケーションを作成することができます。  
  
-   **ユーザー マッピングを作成します。** この種類の操作を実行するには、次の手順を実行します。  
  
    1.  各自の構成に合わせてファイル UserMapping.xml を編集します。  
  
    2.  よう、適切な引数でコマンド ライン ユーティリティ ssomanage.exe を実行します。  
  
        ```  
        ssomanage –createmappings UserMapping.xml  
        ```  
  
     1 つ以上の関連アプリケーションに対して同時に複数のマッピングを作成することができます。  
  
## <a name="comments"></a>コメント  
 このサンプルに付属しているサンプル .xml ファイルを変更した後、特に変更によってファイルに機密情報を追加する場合は、これらのファイルをファイル システム内で十分に保護してください。 たとえば、これらのファイルを不注意で共有ファイルに格納しないようにしてください。  
  
## <a name="see-also"></a>参照  
 [SSO (BizTalk Server Samples フォルダ)](../core/sso-biztalk-server-samples-folder.md)