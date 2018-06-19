---
title: Siebel アプリケーションのセキュリティ保護 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
- data protection
ms.assetid: 8977cbd3-0025-48d4-8203-8e9e72ea7d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b597120de91b6a09fdc26b90a2cb357cdc7dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221970"
---
# <a name="secure-your-siebel-applications"></a>Siebel アプリケーションのセキュリティ保護します。
Siebel システムには、多くの場合、お客様のアカウント詳細などの機密性の高いビジネス情報が含まれています。 使用するアプリケーション、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。 データ保護およびセキュリティは、通常と考えるは次の用語で。  
  
-   *承認*要求者の身元に基づいて、リソースへのアクセスを制御します。  
  
-   *認証*要求者の身元を確認するためのメカニズムを提供します。  
  
-   *データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。  
  
-   *データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。  
  
 問題になるもう 1 つの重要な領域は、ユーザー名パスワード資格情報を提供する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 アダプターでは、これらの資格情報を使用して、Siebel システムへの接続を開きます。 これらの資格情報を指定する接続 URI です。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]より安全な方法でこれらの資格情報を指定するのに使用できる代替のメソッドを提供します。  
  
 このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Siebel システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [Siebel アダプターと BizTalk Server でのセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [Siebel アダプターをセキュリティで保護された使用したプログラミング](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [Siebel アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)