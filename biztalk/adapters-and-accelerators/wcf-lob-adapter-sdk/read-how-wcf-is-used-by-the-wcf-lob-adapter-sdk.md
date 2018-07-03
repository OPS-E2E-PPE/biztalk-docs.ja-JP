---
title: WCF LOB Adapter SDK による WCF の使用方法を読み取る |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 183dd134-7273-4767-bad0-c42ae125985e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8991590d97d70fc0e2090f11f05f8882b0ca3396
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004716"
---
# <a name="read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK による WCF の使用方法を読み取る
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャに依存して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]アダプターの機能を公開し、情報を交換するために必要な基本的なメッセージング サービスを提供するランタイム。 
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]表示することで、アダプターを記述するためのフレームワークを提供します。 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、メタデータ、および接続プールなどの一般的なアダプター要素とそれらを補完するものとします。 サポート ツールなど、エクスペリエンスを強化するためにも含まれています、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] .NET アプリケーションと[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションと[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]します。  
  
 役割です、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]さまざまなコンシューマー アプリケーション、およびをカスタマイズするには、SDK とツールを提供する別のエンドポイント間でメッセージのフローを管理するサービスを公開する構成、およびメッセージ フローを監視します。 たとえば、開発者がの動作をカスタマイズできます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]カスタム メッセージ ハンドラーを使用して、そのチャネルを拡張することによって。  
  
 間のリレーションシップ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]は次の大まかなアーキテクチャの図に示します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/asdk-wcf.gif "ASDK_WCF")  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]の上に構築[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]の拡張機能として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル。 ドメイン固有と簡略化されたオブジェクト モデルとカスタム アダプターを構築するためのツール セットを提供[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 使用してビルドされたアダプターは、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]カスタムとして表示された[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインドします。  
  
 次の図は、指定したアダプターのバインドを使用して、送信メッセージ交換を示します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/58609452-d09e-4dbd-b470-c92a29977858.gif "58609452-d09e-4dbd-b470-c92a29977858")  
  
 次の図は、指定したアダプターのバインドを使用して受信メッセージの交換を示します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b62d5040-7e40-4edd-ac7b-69768131c51b.gif "b62d5040-7e40-4edd-ac7b-69768131c51b")  
  
 詳細については、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルを参照してください[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)します。  
  
## <a name="wcf-services-and-the-wcf-lob-adapter-sdk"></a>WCF サービスと WCF LOB Adapter SDK  
 一般的な開発する際に[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービスは、まず、共有、外部のサービスと通信する方法について説明しているサービスのコントラクトを作成します。 このコントラクトは、基本的に、コレクションと、サービスによって提供される操作にアクセスするために必要なメッセージの構造を指定します。  
  
 このコントラクトは、サービスとして公開すると、[サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)作成に使用できる、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]それを使用するクライアント。 コントラクトは、操作および変更する必要がありますいないメッセージの静的セットに関する情報を提供します。 
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a410af83-ee3b-46d0-9afd-d32970f5ba0a.gif "a410af83-ee3b-46d0-9afd-d32970f5ba0a")  
  
 これに対し、アダプターはビルドを使用して、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]操作と基幹業務システム内で利用可能なデータのコレクションに関するメタデータの動的なセットを提供します。 基幹業務システムは、1 つのコントラクトの説明を取得する操作が多すぎるを多くの場合は、最新のビジネス ニーズに対応する追加された新しい操作がある可能性があります。  
  
 たとえば、基幹業務システムが提供アカウント管理操作。 新しい顧客アカウントの作成を効率化する必要を識別するには後、は、会社は、新しい操作を含める、基幹業務システムを更新します。 使用して構築されたアダプター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]クライアントに提供するメタデータでは、この操作を公開します。  
  
 デザイン時に、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]-ベース アダプターに動的に基幹業務システムのニーズを満たすコントラクトを生成します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2f4d896a-14d9-43f4-8cdc-f816c5eab46d.gif "2f4d896a-14d9-43f4-8cdc-f816c5eab46d")  
  
 ASDK は、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]アダプター コンシューマー デザイン時に動的なコントラクトを生成するためのツール。  
  
 使用して作成されたアダプターにメッセージが流れるときに、実行時に、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプターには受信メッセージに対して、一連のアクションを実行する必要があります多くの場合、できます。 します。 これらのアクションは次のとおりです。  
  
- メッセージに関連するメタデータの検索  
  
- メッセージを開く  
  
- メッセージを解釈します。  
  
- 基幹業務システムで適切な関数の呼び出し  
  
  場合、[!INCLUDE[nextref_btsWinCommFoundation_md](../../includes/nextref-btswincommfoundation-md.md)]サービス、メッセージだけを通過メタデータから解決されることがなく。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle データベースと WCF LOB Adapter SDK](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)