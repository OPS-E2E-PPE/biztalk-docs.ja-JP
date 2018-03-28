---
title: WCF LOB Adapter SDK で作成されたアダプターで WCF セキュリティについて理解 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1ee402b-ffda-42c1-8d85-d7cbe073a307
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf0c62c3d0c37c1f69cb944112ff832dade5ec4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK で作成されたアダプターで WCF のセキュリティを理解します。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]アーキテクチャのチャネルし、は、メッセージング インフラストラクチャとで提供される API を使用します。  WCF LOB アダプターが、ターゲット システムに接続を確立する必要があるし、そのために認証とその他のセキュリティ情報がターゲット システムの接続を確立するために必要なアダプターを構成する必要があります。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 分散プログラミングのプラットフォームは、SOAP メッセージを移動できる多数の異なるノード、SOAP 中継ぎ局、ファイアウォール、および可能性のあるインターネット送信者から基幹業務システムからアダプターにおよび、クライアントにログオンに基づいています。 これは、アダプターと配置のシナリオに対するさまざまなセキュリティの脅威の数が発生する可能性があります。  
  
 セキュリティは、すべてのエンタープライズ アーキテクチャ ソリューションでの主要な役割を果たします。 機密性、整合性、認証、およびセキュリティの脅威からアダプターを保護するために、WCF のセキュリティ モデルで提供される承認機能を活用することができます。 これら 2 つのエンティティ間の通信を保護するには、アダプターと、ターゲット システムの間のメッセージ レベルのセキュリティとトランスポートについても考慮する必要があります。 場合でも、WCF は、豊富な一連の ws-* 仕様、これらの実装の詳細セキュリティ標準では、アダプターは、基幹業務システムによって提供される機能に依存します。  
  
 詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、概要、概念、一般的なシナリオ、およびベスト プラクティスは、「」を参照を含むセキュリティ[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)です。
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)