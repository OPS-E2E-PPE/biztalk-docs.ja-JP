---
title: SQL アプリケーションのセキュリティ保護 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d631bc3ad87e9a8ec8ac51850b7dbe1eb244c140
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224442"
---
# <a name="secure-your-sql-applications"></a>SQL アプリケーションのセキュリティ保護します。
## <a name="overview"></a>概要
SQL Server データベースは、多くの場合、お客様のアカウント詳細などの機密性の高いビジネス情報を含めます。 使用するアプリケーション、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。 データ保護およびセキュリティは、通常と考えるは次の用語で。  
  
-   *承認*要求者の身元に基づいて、リソースへのアクセスを制御します。  
  
-   *認証*要求者の身元を確認するためのメカニズムを提供します。  
  
-   *データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。  
  
-   *データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。  
  
 問題になるもう 1 つの重要な領域は、ユーザー名パスワード資格情報を提供する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 アダプターでは、これらの資格情報を使用して、SQL システムへの接続を開きます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI で指定する資格情報ではできません。 これは、資格情報が誤って公開されるを取得することを防ぎます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]より安全な方法でこれらの資格情報を指定する 2 つの代替メソッドを提供します。  
  
 統合セキュリティ。 ここで、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、Microsoft を使用して[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]資格情報。 このメソッドを使用するこれらの資格情報を受け入れるように SQL server を構成する必要があります。  
  
 エンタープライズ シングル サインオン (SSO)。 詳細については、SSO を使用して、次を参照してください。 [SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。  
  
 このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server とアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [SQL アダプタと BizTalk Server でのセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [SQL アダプタをセキュリティで保護された使用したプログラミング](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [ベスト プラクティス](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)