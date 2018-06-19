---
title: Oracle E-business Suite への接続を作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeeab604-155e-4806-b77a-45319a3f8cc0
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ffdfdc8810024e331598211529f3a594e0169f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216578"
---
# <a name="create-a-connection-to-oracle-e-business-suite"></a>Oracle E-business Suite への接続を作成します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、Oracle E-business Suite への通信を WCF エンドポイントのアドレス使用可能になります。 WCF では、エンドポイントのアドレスは、サービスのネットワークの場所を識別し、として、Uniform Resource Identifier () は通常表現します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接続プロパティが含まれて、URI とは、この場所の表現を[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle E-business Suite への接続を確立するために使用します。 接続 URI を指定する必要がありますとします。  
  
-   チャネル ファクトリまたは WCF チャネル モデルまたは WCF サービス モデルを使用して WCF クライアントまたはサービス ホストを作成する場合を使用してチャネル リスナーを作成します。  
  
-   物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の BizTalk Server ソリューションです。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。  

## <a name="ways-to-connect-to-oracle"></a>Oracle に接続する方法  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]基になる Oracle データベースへの接続を確立するための 2 つの方法をサポートしています。  
  
-   **Tnsnames.ora を使用して**です。 この方法では、アダプター クライアントによって提供される URI の接続には、tnsnames.ora ファイルに入力された net サービス名のみが含まれています。 アダプターは、net サービス名のエントリ、ファイルからサーバー名、サービス名、ポート番号など、接続パラメーターを抽出します。 このアプローチを使用するのには、tnsnames.ora ファイルに、Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成しなければなりません。  
  
    > [!IMPORTANT]
    >  Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [Oracle E-business Suite 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)する場合は、複数の 39 文字を含めることはできませんトランザクションで操作を実行します。 したがって場合は、トランザクションで操作を実行することを確認、 **DataSourceName**パラメーター値は 39 文字未満です。  
  
-   **Tnsnames.ora を使用せず**です。 この方法では、アダプターのクライアントは、接続 URI 内で直接接続パラメーターを入力します。 これは、操作では、tnsnames.ora ファイル、クライアント コンピューター上に存在する net サービス名は必要ありません。 クライアント コンピューターに存在している tnsnames.ora ファイルが、この方法でもは必要はありません。  
  
    > [!IMPORTANT]
    >  トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限によるものです。  

## <a name="in-this-section"></a>このセクションの内容    
 以下のトピックとの間の接続を確立する方法を説明する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]と Oracle E-business Suite:  
  
-   [Oracle クライアント E-business Suite アダプターを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md): cconfiguring (、tnsnames.ora を使用して接続を確立する場合にのみ必要)、Oracle クライアントに tnsnames.ora の使用について  
  
-   [Oracle E-business Suite 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md): 接続のプロパティと、Oracle E-business Suite 接続 URI の構造について
  
-   [Windows 認証を使用して Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md): Windows 認証を使用して oracle データベースへの接続に関する情報
  