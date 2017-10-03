---
title: "WCF LOB Adapter SDK による WCF を使用する方法を読み取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 183dd134-7273-4767-bad0-c42ae125985e
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb84124213df8cf1bd401ab80db25586f5ca4534
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK による WCF を使用する方法を読み取る
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャに依存して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]アダプタの機能を公開し、情報を交換するために必要な基本的なメッセージング サービスを提供するランタイム。 
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提示でそれらのアダプターを作成するためのフレームワークを提供[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メタデータと接続プールなどの一般的なアダプター要素とそれらを補完するものとします。 エクスペリエンスを向上などのサポート ツールで構成されます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]は、.NET アプリケーションおよび[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションおよび[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]です。  
  
 役割です、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]さまざまな処理アプリケーション、別のエンドポイント間でメッセージのフローを管理し、をカスタマイズするには、SDK とツールを提供するサービスを公開する構成、およびメッセージ フローを監視します。 たとえば、開発者がの動作をカスタマイズできます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]カスタム メッセージのハンドラーを使用して、チャネルを拡張しています。  
  
 間のリレーションシップ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]次の大まかなアーキテクチャの図に示します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/asdk-wcf.gif "ASDK_WCF")  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]の上に構築[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]の拡張機能として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル。 ドメイン固有と簡略化されたオブジェクト モデルとカスタム アダプターを構築するためのツール セットを提供[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 使用してビルドされたアダプターは、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]カスタムとして提示[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインドします。  
  
 次の図は、指定したアダプターのバインドを使用して、送信メッセージ交換を示します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/58609452-d09e-4dbd-b470-c92a29977858.gif "58609452-d09e-4dbd-b470-c92a29977858")  
  
 次の図は、指定したアダプターのバインドを使用して、着信メッセージ交換を示します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b62d5040-7e40-4edd-ac7b-69768131c51b.gif "b62d5040-7e40-4edd-ac7b-69768131c51b")  
  
 詳細については、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデルをチャネルは、「[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)です。  
  
## <a name="wcf-services-and-the-wcf-lob-adapter-sdk"></a>WCF サービスと WCF LOB Adapter SDK  
 一般的な開発するときに[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービスは、まず、サービスと通信する方法を説明する外部と共有されているサービスのコントラクトを作成します。 このコントラクトは、本質的には、コレクションと、サービスによって提供される操作へのアクセスに必要なメッセージの構造を指定します。  
  
 このコントラクトがサービスとして公開されると、[サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)の作成に使用できる、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]それを利用するクライアント。 コントラクトは、操作および変更する必要がありますいないメッセージの静的セットに関する情報を提供します。 
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a410af83-ee3b-46d0-9afd-d32970f5ba0a.gif "a410af83-ee3b-46d0-9afd-d32970f5ba0a")  
  
 これに対し、アダプターはビルドを使用して、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]操作データと基幹業務システム内で使用できるデータのコレクションに関するメタデータの動的なセットを提供します。 基幹業務システム 1 つのコントラクトで説明する操作が多すぎることがよくありますし、可能性があります新しい操作に追加出現するビジネス ニーズに対応します。  
  
 たとえば、基幹業務システム可能性がありますアカウントを指定の管理操作。 新しいお客様のアカウントの作成を簡素化する必要性を識別するには後、は、会社は、新しい操作を含める基幹業務システムを更新します。 使用して構築されたアダプター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]はクライアントに、メタデータでこの操作を公開します。  
  
 デザイン時に、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]-ベース アダプターを基幹業務システムのニーズを満たすために動的にコントラクトが生成されます。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2f4d896a-14d9-43f4-8cdc-f816c5eab46d.gif "2f4d896a-14d9-43f4-8cdc-f816c5eab46d")  
  
 ASDK 提供[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]コントラクトを生成する動的デザイン時にアダプターのコンシューマー向けのツールです。  
  
 使用して作成されたアダプターにメッセージを流れる場合、実行時に、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプターには受信メッセージに対して、一連のアクションを実行する必要があります多くの場合、できます。 します。 これらのアクションは次のとおりです。  
  
-   メッセージに関連するメタデータの検索  
  
-   メッセージを開く  
  
-   メッセージを解釈します。  
  
-   基幹業務システムで適切な関数の呼び出し  
  
 場合、[!INCLUDE[nextref_btsWinCommFoundation_md](../../includes/nextref-btswincommfoundation-md.md)]サービス、メッセージだけでなくを通過メタデータを通じて解決中です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle データベースと WCF LOB Adapter SDK](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)