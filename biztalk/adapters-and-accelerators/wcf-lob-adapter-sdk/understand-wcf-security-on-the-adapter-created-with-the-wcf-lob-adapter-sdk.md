---
title: WCF LOB Adapter SDK で作成されたアダプターで WCF セキュリティの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1ee402b-ffda-42c1-8d85-d7cbe073a307
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b34be29b74b10d5b9768cff5bc40a26abe41dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362721"
---
# <a name="understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK で作成されたアダプターで WCF セキュリティを概要します。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルのアーキテクチャと、メッセージング インフラストラクチャとそれを提供する API に依存しています。  WCF LOB アダプターを対象のシステムへの接続を確立する必要があるし、は認証とターゲット システムに接続するために必要なその他のセキュリティ情報と、アダプターを構成するために必要なためです。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 分散プログラミングのプラットフォームはアダプターに、クライアントへのログオンと基幹業務システムから多数の異なるノード、SOAP 中継ぎ局、ファイアウォール、および可能性のあるインターネットの途中で移動できる SOAP メッセージに基づいています。 これは、数、アダプターと展開シナリオに対するさまざまなセキュリティの脅威が発生する可能性があります。  
  
 セキュリティは、すべてのエンタープライズ アーキテクチャ ソリューションでの主要な役割を果たします。 機密性、整合性、認証、およびセキュリティの脅威からアダプターをセキュリティ保護するための WCF セキュリティ モデルで提供される承認機能を活用することができます。 トランスポートおよびこれら 2 つのエンティティ間の通信を保護するには、アダプターと、ターゲット システムの間のメッセージ レベルのセキュリティも考慮する必要があります。 場合でも、WCF は ws-の豊富なセットを提供します * の仕様、これらの実装の詳細セキュリティ標準では、アダプターは、基幹業務システムによって提供される機能に依存します。  
  
 詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、概要、概念、一般的なシナリオ、およびベスト プラクティスは、参照を含むセキュリティ[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)します。
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)