---
title: "WCF LOB Adapter SDK を説明するチュートリアル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99002b01-da8a-483e-ada3-1ffbe9cd7357
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3efc47a5df445e18e4a78a005c31791fe1f1fa24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorials-to-learn-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を説明するチュートリアル
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]チュートリアルを使用する方法に関する情報を格納する[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]開発機能豊富な基幹業務アダプタが、企業内でエンタープライズ アプリケーション統合を容易になります。 使用して、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、WCF バインディングで使用できる任意のアプリケーションで使用できる操作および公開するデータを含む[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
 チュートリアルには、構築されています。 定義済み操作のセットの単純な例が含まれています。 これらのチュートリアルを完了する使用可能なビジネス システムの実際の行は不要です。 ただし、チュートリアルで詳細情報は、送信ハンドラーを記述する以降についてメタデータから、アダプター開発のニーズに適用できます。  

> [!TIP]
> 完了したエコー アダプターが、BizTalk のインストール ファイルに含まれる`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`または`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`です。
  
 重要な部分を使用する方法については、以下のチュートリアルを使用して、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
-   [チュートリアル 1: エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。 基幹業務システムとして機能する定義済みのメソッドのセットから文字列操作を公開するアダプターの作成の詳細な手順について説明します。 アダプターは、多くの一般的なハンドラーの実装を提供、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]検索、参照、着信および発信の操作などです。 このチュートリアルの正常に完了、機能のアダプターがあります。  
  
-   [チュートリアル 2: .NET からエコー アダプターの消費](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)です。 詳細な手順についてで開発されたエコー アダプターの消費[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).NET プロジェクトからです。 新しいプロジェクトにアダプター サービス参照を追加し、エコー アダプターの受信と送信の動作をテスト コードを提供します。  
  
-   [チュートリアル 3: IIS でエコー アダプターをホストしている](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)です。 詳細な手順についてで開発されたエコー アダプターをホストする[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)インターネット インフォメーション サービス (IIS) で処理します。 ホストされているアダプターの EchoString 操作を使用するのに単純なクライアント アプリケーションを作成するのに svcutil.exe (ServiceModel メタデータ ユーティリティ) が使用されます。  
  
 これらのチュートリアルの主な機能の一部を把握するための構造化されたアプローチを提供する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 に関する知識がないを完了する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]または[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。 ただしは、詳しくアダプター デザインの概念を理解でアダプター デザインが容易にする方法を理解していて、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 詳細については、以下をご覧ください。  
  
-   [WCF の開発者の一般的なタスクの LOB アダプター SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/common-developer-tasks-for-the-wcf-lob-adapter-sdk.md)  
  
-   [WCF LOB Adapter SDK の主要なコンポーネント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/key-components-of-the-wcf-lob-adapter-sdk.md)  
  
 これらのチュートリアルを開始する前に、要件を確認する必要があります[チュートリアルを開始する前に](../../core/before-you-begin-the-tutorial.md)です。  
  
 
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チュートリアルを開始する前に](../../core/before-you-begin-the-tutorial.md)  
  
-   [チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)  
  
-   [チュートリアル 2: .NET からエコー アダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)  
  
-   [チュートリアル 3: IIS でエコー アダプターをホストします。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の概要](../../core/getting-started-with-biztalk-server.md)