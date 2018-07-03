---
title: Oracle E-business Suite への接続の作成 |Microsoft Docs
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
ms.openlocfilehash: c0da85f6c0968eb7257e980bdbd65a48fcf734f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973307"
---
# <a name="create-a-connection-to-oracle-e-business-suite"></a>Oracle E-business Suite への接続を作成します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、Oracle E-business Suite への通信を WCF エンドポイントのアドレスを使用できます。 WCF では、エンドポイント アドレスは、サービスのネットワークの場所を識別しする Uniform Resource Identifier (URI) としては通常表現します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接続プロパティを格納する、URI として、この場所を表します[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle E-business Suite への接続を確立するために使用します。 接続 URI を指定する必要がありますとします。  
  
- チャネル ファクトリまたは WCF チャネル モデルまたは WCF サービス モデルを使用して WCF クライアントまたはサービス ホストを作成する場合を使用してチャネル リスナーを作成します。  
  
- 物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは WCF サービス モデル ソリューションの WCF サービスのインターフェイスを生成します。  
  
- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の BizTalk Server ソリューションです。  
  
- WCF クライアント クラスまたは WCF サービス モデル ソリューションの WCF サービスのインターフェイスを生成するには、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用します。  

## <a name="ways-to-connect-to-oracle"></a>Oracle に接続する方法  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]基になる Oracle データベースへの接続を確立する 2 つの方法をサポートしています。  
  
-   **Tnsnames.ora を使用して**します。 この方法では、アダプター クライアントによって提供された URI の接続には、tnsnames.ora ファイルに入力された net サービス名のみが含まれています。 アダプターは、ファイルの net サービス名のエントリから、サーバー名、サービス名、ポート番号など、接続パラメーターを抽出します。 このアプローチを使用するには、tnsnames.ora ファイルで Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成する必要があります。  
  
    > [!IMPORTANT]
    >  Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [Oracle E-business Suite 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)する場合は、複数の 39 文字を含めることはできませんトランザクションで操作を実行します。 そのため、トランザクションで操作を実行している場合ことを確認、 **DataSourceName**パラメーターの値は 39 文字未満です。  
  
-   **Tnsnames.ora を使用せず**します。 この方法では、アダプターのクライアントは、直接接続 URI の接続パラメーターを入力します。 これは、クライアント コンピューターの tnsnames.ora ファイルに存在する net サービス名には必要ありません。 この方法は、クライアント コンピューターに存在している、tnsnames.ora ファイルをも必要ありません。  
  
    > [!IMPORTANT]
    >  トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限です。  

## <a name="in-this-section"></a>このセクションの内容    
 次のトピックとの間の接続を確立する方法を説明する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]と Oracle E-business Suite:  
  
-   [Oracle E-business Suite アダプターのクライアントの構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md): cconfiguring (、tnsnames.ora を使用して、接続を確立する場合にのみ必要)、Oracle クライアントを tnsnames.ora の使用について  
  
-   [Oracle E-business Suite 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md): 接続のプロパティと Oracle E-business Suite 接続 URI の構造について
  
-   [Windows 認証を使用して Oracle E-business Suite に接続する](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md): Windows 認証を使用して Oracle への接続に関する情報
  