---
title: Oracle データベース アプリケーションのセキュリティ保護 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8601463c02e32221c369023f05ed2fd3731bb4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214706"
---
# <a name="secure-your-oracle-database-applications"></a>Oracle データベース アプリケーションのセキュリティ保護します。
## <a name="data-protection-and-security-overview"></a>データの保護およびセキュリティの概要
多くの場合、データベースには、お客様のアカウント詳細などの機密性の高いビジネス情報が含まれています。 使用するアプリケーション、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。 データ保護およびセキュリティは、通常と考えるは次の用語で。  
  
-   *承認*要求者の身元に基づいて、リソースへのアクセスを制御します。  
  
-   *認証*要求者の身元を確認するためのメカニズムを提供します。  
  
-   *データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。  
  
-   *データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。  
  
 問題になるもう 1 つの重要な領域は、ユーザー名パスワード資格情報を提供する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 アダプターでは、これらの資格情報を使用して、Oracle データベースへの接続を開きます。 これらの資格情報を指定する接続 URI です。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]より安全な方法でこれらの資格情報を指定するのに使用できる代替のメソッドを提供します。  
  
 このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベースとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [Oracle データベース アダプターと BizTalk Server でのセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [Oracle データベース アダプターをセキュリティで保護された使用したプログラミング](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [ベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)