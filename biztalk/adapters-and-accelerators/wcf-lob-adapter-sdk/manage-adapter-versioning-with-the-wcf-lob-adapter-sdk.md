---
title: "WCF LOB Adapter SDK と、アダプター バージョンの管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb596fdd-251c-4978-9f33-cf2883d281d8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8d5d13c37f683a118484c9c08fa90c13a95533
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manage-adapter-versioning-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK と、アダプター バージョンを管理します。
アダプターとその有効期間中に、可能性のある数回の初期デプロイ後アダプター (およびが公開するエンドポイント) は、さまざまな理由を変更する必要があります。 これらの理由には、ビジネス ニーズ、情報テクノロジの要件、または基幹業務システムまたはアダプター自体に関する問題の変更が含まれます。 使用して記述されているアダプターのバージョン管理を処理するためのさまざまな方法について説明、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。  
  
## <a name="versioning-and-windows-communication-foundation"></a>バージョン管理および Windows Communication Foundation  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]に基づいて構築されており、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]システム間でメッセージを交換するためのインフラストラクチャに依存します。 機構を使用している[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を公開するバージョンを実行できますサービスとデータの両方のコントラクト。 詳細については、サービスのバージョン管理のベスト プラクティスを含め、次を参照してください。[サービスのバージョン管理](http://go.microsoft.com/fwlink/?LinkId=85497)で、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]オンライン参照します。 詳細については、データ コントラクトのバージョン管理のベスト プラクティスを含め、次を参照してください。[データ コントラクトのバージョン管理](http://go.microsoft.com/fwlink/?LinkId=120177)で、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]オンライン参照します。  
  
## <a name="versioning-scenarios"></a>バージョン管理のシナリオ  
 2 つのプライマリ バージョン管理シナリオはあります。  
  
-   1 つのアダプター バージョンには、ターゲット システムの複数のバージョンがサポートしています。  
  
-   2 つ以上のアダプター バージョンでは、同じシステム上または 2 つ以上の異なるシステムをサポートします。  
  
 場合、アダプターの新しいバージョンをリリースする必要がありますもへの更新、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]既存の機能に影響します。  
  
 これらの各シナリオには、異なるバージョン管理の戦略が必要です。  
  
> [!NOTE]
>  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]特定のバージョン管理シナリオは強制されません。 アダプターのバージョン管理の要件を決定する開発者に任されています。  
  
### <a name="one-adapter-supports-multiple-versions-of-target-system"></a>1 つのアダプターは、ターゲット システムの複数のバージョンをサポートしています。  
 アダプターは、ターゲット システムの複数のバージョンをサポートするときに、必要なバージョンを識別するために使用する 1 つまたは複数のバインドのプロパティを公開する必要があります。 たとえば、アダプターは、対象システムのベンダーから提供された複数の通信ライブラリをサポートする可能性があります。 アダプターのコンシューマー"LibraryVersion"をという名前のカスタム バインドのプロパティを使用して、デプロイ環境、またはその他の要件に基づいて、使用するライブラリを選択できます。  
  
### <a name="two-or-more-adapters-support-one-version-of-target-system"></a>2 つまたは複数のアダプターは、ターゲット システムの 1 つのバージョンをサポートします。  
 各アダプターが、一意のスキームを使用するこの例では、(ContosoV1://および ContosoV2://) と (ContosoV1Binding および ContosoV2Binding) は、一意のバインディング名。 ベンダーは、スキームとバインドも名前 (たとえば、Microsoft.ContosoV1:// および Microsoft.ContosoV1Binding) 名を使用を検討してください。  
  
### <a name="new-versions-of-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK の新しいバージョン  
 ときに新しいバージョンの[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]がリリースされることができますので、アダプターを再コンパイルしなくても新しいバージョンをインストールする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]リリースは、旧バージョンと互換性のあるをします。 ただし、新しいリリースを調べるには、アダプターが依存する機能の変更がある場合、アダプターの実装からメリットを得られる新しい機能がある場合を評価する必要があります。  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して、開発のベスト プラクティス](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)