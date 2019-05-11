---
title: WCF LOB アダプター SDK を使用した、アダプター バージョンの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb596fdd-251c-4978-9f33-cf2883d281d8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e444008cb43c3638bbab31f665615880e346229e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363577"
---
# <a name="manage-adapter-versioning-with-the-wcf-lob-adapter-sdk"></a>WCF LOB アダプター SDK を使用した、アダプター バージョンを管理します。
アダプターとその有効期間中に、可能性のある数回の初期デプロイ後のアダプター (および公開されるエンドポイント) は、さまざまな理由から変更する必要があります。 これらの理由からには、ビジネス ニーズ、情報テクノロジの要件、または基幹業務システムまたはアダプター自体の問題の変更が含まれます。 このトピックでは、アダプターを使用して記述されているのバージョン管理を処理するためのさまざまな方法を説明します、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。  
  
## <a name="versioning-and-windows-communication-foundation"></a>バージョン管理と Windows Communication Foundation  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]基づいて[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]システム間でメッセージを交換するためのインフラストラクチャに依存しています。 メカニズムを使用している[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を公開するバージョンを実行できますサービスとデータの両方のコントラクト。 詳細については、サービスのバージョン管理のベスト プラクティスを含め、次を参照してください。[サービスのバージョン管理](http://go.microsoft.com/fwlink/?LinkId=85497)で、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]オンライン参照。 詳細については、データ コントラクトのバージョン管理のベスト プラクティスを含め、次を参照してください。[データ コントラクトのバージョン管理](http://go.microsoft.com/fwlink/?LinkId=120177)で、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]オンライン参照。  
  
## <a name="versioning-scenarios"></a>バージョン管理のシナリオ  
 2 つのプライマリ バージョン管理シナリオがあります。  
  
- 1 つのアダプター バージョンでは、ターゲット システムの複数のバージョンをサポートします。  
  
- 2 つ以上のアダプター バージョンでは、同じシステム上または 2 つまたは複数の異なるシステムをサポートします。  
  
  場合、アダプターの新しいバージョンをリリースする必要がありますもへの更新、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]既存機能に影響します。  
  
  これらの各シナリオには、異なるバージョン管理戦略が必要です。  
  
> [!NOTE]
>  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]特定のバージョン管理シナリオを適用しません。 開発者がアダプターのバージョン管理の要件を決定します。  
  
### <a name="one-adapter-supports-multiple-versions-of-target-system"></a>1 つのアダプターは、ターゲット システムの複数のバージョンをサポートしています。  
 アダプターには、ターゲット システムの複数のバージョンがサポートされている場合は、目的のバージョンを識別するために使用できる 1 つまたは複数のバインドのプロパティを公開する必要があります。 たとえば、アダプターは、ターゲット システムのベンダーから提供された複数の通信ライブラリをサポートする可能性があります。 配置環境またはその他の要件に基づいて、使用するライブラリ"LibraryVersion"をという名前のカスタム バインド プロパティを使用して、アダプターのコンシューマーを選択できます。  
  
### <a name="two-or-more-adapters-support-one-version-of-target-system"></a>2 つまたは複数のアダプターは、ターゲット システムの 1 つのバージョンをサポートします。  
 ここでは、各アダプターが、一意のスキームを使用する必要があります (ContosoV1://と ContosoV2://) と一意のバインドの名前 (ContosoV1Binding および ContosoV2Binding)。 ベンダーは、スキームとバインド名も (たとえば、Microsoft.ContosoV1:// と Microsoft.ContosoV1Binding) 名を使用を検討してください。  
  
### <a name="new-versions-of-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK の新しいバージョン  
 ときに新しいバージョンの[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]がリリースされるができるため、アダプターを再コンパイルしなくても新しいバージョンをインストールする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]リリースは下位互換性のあるをします。 ただし、アダプターが依存している機能の変更がある場合、または、アダプターの実装からメリットを得られる新しい機能がある場合を判断する、新しいリリースを評価する必要があります。  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して開発のベスト プラクティス](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)