---
title: "BizTalk Server を使用して JSON メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6db1421-9478-477c-8645-09eefba06246
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c2e4adac7c7d1503a49f68208e45e09f86b67ac
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="processing-json-messages-using-biztalk-server"></a>BizTalk Server を使用した JSON メッセージの処理
> [!NOTE]
>  このチュートリアルは、BizTalk Server にのみ適用されます。  
  
 このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して JSON メッセージを処理する方法を示します。 このチュートリアルでは、カスタム パイプライン コンポーネント、BizTalk Server で使用できるようになりましたを使用します。 これらのパイプライン コンポーネントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションでメッセージを受信して JSON メッセージを XML に変換し、メッセージの送信時にメッセージを XML から JSON に変換します。  
  
## <a name="what-does-this-tutorial-do"></a>このチュートリアルの目的  
 次の内容を次の順序で実行する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を作成して、JSON の処理方法を示します:  
  
1.  JSON 注文書を受信して、受信パイプラインで JSON デコーダー コンポーネントを使用して JSON メッセージを XML メッセージに変換します。  
  
2.  マップを使用して XML 注文書を XML 請求書に変換します。  
  
3.  送信パイプラインで、JSON エンコーダーを使用して XML 請求書を JSON 請求書に変換して送信します。  
  
 ![BizTalk Server での JSON メッセージの処理](../core/media/btsjson-flow.png "BTSJSON_Flow")  
  
## <a name="how-to-use-this-tutorial"></a>このチュートリアルの使用方法  
 このチュートリアルが構築されています。 サンプル (**BTSJSON**) からダウンロードすることができます、 [MSDN コード ギャラリー](http://go.microsoft.com/fwlink/?LinkId=403197)です。 サンプルを使用してチュートリアルを進めることで、サンプルが構築された方法を理解しやすくなります。 または、このチュートリアルで独自のソリューションを作り上げることもできます。 このチュートリアルは、このソリューションがどのように構築されたかを理解できるよう、2 つ目のアプローチに向けて作成されています。 また、このチュートリアルでは、可能な限りサンプルに合わせて、サンプルで使用されているのと同じアイテム名 (スキーマ、変換など) を使用しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [JSON メッセージの XSD スキーマの生成](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [JSON メッセージ処理用のカスタム パイプラインの作成](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [BizTalk Server のオーケストレーションの作成](../core/create-a-biztalk-server-orchestration.md)  
  
-   [アプリの配置およびテスト](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server チュートリアル](../core/biztalk-server-tutorials.md)