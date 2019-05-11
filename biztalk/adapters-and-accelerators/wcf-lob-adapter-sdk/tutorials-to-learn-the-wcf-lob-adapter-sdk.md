---
title: WCF LOB Adapter SDK についてのチュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99002b01-da8a-483e-ada3-1ffbe9cd7357
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa80199a20d040ac3542769f66db4ddfee961e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363009"
---
# <a name="tutorials-to-learn-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK についてのチュートリアル
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]チュートリアルを使用する方法に関する情報を含む[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]機能豊富な基幹業務アダプタを企業内でエンタープライズ アプリケーション統合を容易に開発します。 使用して、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、操作および公開するデータは、WCF バインドを使用できる任意のアプリケーションで使用できるなど[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
 チュートリアルには、一連の定義済みの操作を中心に構築された簡単な例が含まれます。 これらのチュートリアルを完了する使用可能なビジネス システムの実際の行を使用する必要はありません。 ただし、詳細については、チュートリアルは、送信ハンドラーの記述や、他の製品についてのメタデータから、アダプター開発のニーズに適用できます。  

> [!TIP]
> 完了したエコー アダプターので、BizTalk のインストール ファイルに含まれている`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`または`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`します。
  
 重要な部分を使用する方法については、次のチュートリアルを使用して、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
- [チュートリアル 1:エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)します。 基幹業務システムとして機能する定義済みのメソッドのセットから文字列操作を公開するアダプターを作成するための手順について説明します。 アダプターは、多くの一般的なハンドラーの実装を提供します、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]検索、参照、受信と送信の操作など。 このチュートリアルの正常な完了には、機能のアダプターがあります。  
  
- [チュートリアル 2: .NET からエコー アダプターを使用](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)します。 開発されたエコー アダプターの使用の手順について説明します[チュートリアル 1。エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).NET プロジェクトから。 新しいプロジェクトへのアダプター サービス参照の追加をエコー アダプターの受信と送信操作をテストするコードを提供します。  
  
- [チュートリアル 3: IIS でエコー アダプターをホストしている](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)します。 開発されてエコー アダプターをホストしている場合は、手順を説明します[チュートリアル 1。エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)インターネット インフォメーション サービス (IIS) で処理します。 Svcutil.exe (ServiceModel メタデータ ユーティリティ) を使用しても、ホストされているアダプターの EchoString 操作を使用する単純なクライアント アプリケーションを作成します。  
  
  これらのチュートリアルの主な機能の一部を理解するための体系化されたアプローチを提供する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 に関する情報なしで完了できますが、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]または[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]します。 ただし、詳細については、アダプターのデザインの概念を理解しでアダプターのデザインを促進する方法を理解する場合、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 詳細については、以下をご覧ください。  
  
- [WCF の開発者の一般的なタスクの LOB アダプター SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/common-developer-tasks-for-the-wcf-lob-adapter-sdk.md)  
  
- [WCF LOB Adapter SDK の主要なコンポーネント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/key-components-of-the-wcf-lob-adapter-sdk.md)  
  
  これらのチュートリアルを開始する前の要件を確認する必要があります[チュートリアルを開始する前に](../../core/before-you-begin-the-tutorial.md)します。  
  
 
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チュートリアルを開始する前に](../../core/before-you-begin-the-tutorial.md)  
  
-   [チュートリアル 1:エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)  
  
-   [チュートリアル 2: .NET からエコー アダプターを使用する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)  
  
-   [チュートリアル 3: IIS でエコー アダプターをホストする](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の概要](../../core/getting-started-with-biztalk-server.md)