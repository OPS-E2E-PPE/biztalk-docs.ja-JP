---
title: "JSON メッセージの XSD スキーマの生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b450c74f7d2eda6d3b688c40d0f8e8cde5c66d3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generate-an-xsd-schema-for-json-message"></a>JSON メッセージの XSD スキーマの生成
> [!NOTE]
>  このチュートリアルは、[!INCLUDE[prague](../includes/prague-md.md)] のみを対象としています。  
  
 このソリューションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリが JSON メッセージを受信します。 アプリがメッセージを処理する前に、メッセージを XSD スキーマに変換する必要があります。 変換には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の JSON メッセージから XSD スキーマを作成する JSON スキーマ ウィザードを使用します。  
  
1.  Visual Studio で、新しい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを作成します。  
  
2.  ソリューション エクスプ ローラーでプロジェクト名を右クリックして >**追加** > **新しい項目の** > **JSON スキーマ ウィザード**です。 スキーマの名前を指定 (`PO.xsd`) をクリックして**追加**です。  
  
3.  JSON スキーマ ウィザードの [ようこそ] ページでをクリックして**次**です。  
  
4.  JSON スキーマの情報ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリに送信される JSON 注文書ファイルの場所を指定します。 ターゲットの名前空間のルート ノード名を指定し、をクリックして**完了**です。  
  
     ![JSON の XSD スキーマを生成された](../core/media/btsjson-wizard.png "BTSJSON_Wizard")  
  
5.  指定した名前のスキーマが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトに追加されます。 生成されたスキーマ ファイル (**PO.xsd**) サンプルを使用しても用意されています。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)