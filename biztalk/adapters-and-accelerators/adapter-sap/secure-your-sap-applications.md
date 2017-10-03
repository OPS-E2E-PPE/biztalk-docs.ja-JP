---
title: "SAP アプリケーションのセキュリティ保護 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security and protection
ms.assetid: 9f0fb2a2-d6e2-4561-8472-c0bf682a4798
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f5fe75acf7b033d0f957c7742f52ba521bdde7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-sap-applications"></a>SAP アプリケーションのセキュリティ保護します。
SAP システムは、お客様のアカウント詳細などの機密性の高いビジネス情報を含めることができます。 使用するアプリケーション、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。 データ保護およびセキュリティは、通常と考えるは次の用語で。  
  
-   *承認*要求者の身元に基づいて、リソースへのアクセスを制御します。  
  
-   *認証*要求者の身元を確認するためのメカニズムを提供します。  
  
-   *データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。  
  
-   *データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。  
  
 このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)
  
-   [SAP アダプターと BizTalk Server でのセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)
  
-   [SAP アダプターをセキュリティで保護された使用したプログラミング](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)
  
-   [SAP アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)