---
title: JSON メッセージの XSD スキーマの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f44b18593e756fe1ed6e05e03d62e498f66c0a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387769"
---
# <a name="generate-an-xsd-schema-for-json-message"></a>JSON メッセージの XSD スキーマを生成します。
> [!NOTE]
>  このチュートリアルは、BizTalk Server にのみ適用されます。  
  
 このソリューションで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション JSON メッセージを受信します。 アプリケーションでは、メッセージを処理できますが、前に、XSD スキーマに変換する必要があります。 これを行うに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]JSON メッセージから XSD スキーマを作成する JSON スキーマ ウィザードを提供します。  
  
1. Visual Studio で、作成、新しい[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。  
  
2. ソリューション エクスプ ローラーでプロジェクト名を右クリックして >**追加** > **新しい項目の** > **JSON スキーマ ウィザード**します。 スキーマの名前を指定 (`PO.xsd`)、をクリックし、**追加**します。  
  
3. JSON スキーマ ウィザードの [ようこそ] ページで、をクリックして**次**します。  
  
4. JSON スキーマ情報 ページに送信される JSON 注文書順序ファイルの場所を指定します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。 ターゲットの名前空間のルート ノード名を指定し、**完了**します。  
  
    ![JSON の生成された XSD スキーマ](../core/media/btsjson-wizard.png "BTSJSON_Wizard")  
  
5. 指定した名前のスキーマが追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 生成されたスキーマ ファイル (**PO.xsd**) サンプルを使用しても提供されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)