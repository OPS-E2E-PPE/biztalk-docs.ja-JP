---
title: BizTalk Server を使用して JSON メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6db1421-9478-477c-8645-09eefba06246
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7336b515d196fadc6e8e6cc4fe0bcf500b883189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396982"
---
# <a name="processing-json-messages-using-biztalk-server"></a>BizTalk Server を使用して JSON メッセージの処理
> [!NOTE]
>  このチュートリアルは、BizTalk Server にのみ適用されます。  
  
 このチュートリアルを使用して JSON メッセージを処理する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 チュートリアルでは、BizTalk Server で今すぐ使用できるカスタム パイプライン コンポーネントを使用します。 これらのパイプライン コンポーネントでは、JSON メッセージを XML に変換 (にメッセージを受信中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションとメッセージを送信するときにメッセージを XML から JSON に変換します。  
  
## <a name="what-does-this-tutorial-do"></a>このチュートリアルの目的が何か。  
 JSON の処理を示すためには、作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定の順序で、次を行うこと。  
  
1. JSON 注文書を受信し、受信パイプラインで XML メッセージに JSON メッセージを変換する JSON デコーダー コンポーネントを使用します。  
  
2. マップを使用して XML 請求書には、XML 注文書を変換します。  
  
3. 送信パイプラインでに JSON 請求書の XML を変換する JSON エンコーダーを使用して請求書し、送信されます。  
  
   ![BizTalk Server で JSON メッセージの処理](../core/media/btsjson-flow.png "BTSJSON_Flow")  
  
## <a name="how-to-use-this-tutorial"></a>このチュートリアルを使用する方法は?  
 このチュートリアルは、サンプルに構築されています (**BTSJSON**) からダウンロードできますが、 [MSDN コード ギャラリー](http://go.microsoft.com/fwlink/?LinkId=403197)します。 サンプルを使用して、サンプルの構築方法を理解するには、このチュートリアルを参照してください。 または、独自のソリューション地上-アップを作成するこのチュートリアルを使用する可能性があります。 このソリューションの構築方法を理解できるようにこのチュートリアルの 2 番目のアプローチが対象です。 また、可能な限り、チュートリアルはサンプルを使用して一貫性のある使用してアーティファクト (スキーマ、変換など) に同じ名前として、サンプルで使用されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [JSON メッセージの XSD スキーマの生成](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [JSON メッセージ処理用のカスタム パイプラインの作成](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [BizTalk Server のオーケストレーションの作成](../core/create-a-biztalk-server-orchestration.md)  
  
-   [アプリの配置およびテスト](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server チュートリアル](../core/biztalk-server-tutorials.md)