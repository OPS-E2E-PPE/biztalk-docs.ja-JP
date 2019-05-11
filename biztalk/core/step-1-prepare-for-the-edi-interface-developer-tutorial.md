---
title: 手順 1:EDI インターフェイス開発チュートリアルの準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9be1bddf-d673-4054-87f5-0205b8b5cc0d
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01678bb342909d13beb15141765b789b12a0687
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392801"
---
# <a name="step-1-prepare-for-the-edi-interface-developer-tutorial"></a>手順 1:EDI インターフェイス開発チュートリアルを準備します。
![手順 9 の 1](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  
  
 EDI インターフェイス開発チュートリアルは、1 台のコンピューターで実行されます。 チュートリアルを準備するには、インストールして構成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」の説明に従って[BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)します。 BizTalk EDI アプリケーションへの参照を追加することも必要があります。  
  
> [!NOTE]
>  このチュートリアルが機能するには、IIS 7.5 または IIS 8 を使用するプラットフォームで実行する必要があります。  
  
 EDI インターフェイス開発チュートリアルに必要なファイルにある、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer Tutorial フォルダ。 フォルダーおよびチュートリアルに必要なファイルは次のとおりです。  
  
|Folder\File|目的|  
|------------------|-------------|  
|\SDK\EDI Interface Developer Tutorial\EDI Inbound Processing.sln|このメッセージング シナリオを作成する Visual Studio で使用するソリューション ファイル|  
|\SDK\EDI Interface Developer Tutorial\keyfile.snk|ソリューション ファイルに指定されたアセンブリ キー ファイル|  
|\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt|ソリューションのテストに使用するサンプル メッセージ ファイル (バージョン 4010 850)|  
|\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm|850 メッセージ データを注文システムで必要な形式に変換する BizTalk マップ。|  
|\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp|注文システムにメッセージを送信するためのテスト メッセージを処理する送信パイプラインです。|  
|\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\X12_00401_850.xsd|テスト メッセージの 850 スキーマです。|  
\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM|Fabrikam から受信 850 メッセージの受信場所フォルダー|  
|\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem|フォルダーを送信 850 メッセージの送信先、注文システムのバック エンド アプリケーションを表す|  
|\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997|フォルダーを 997 受信確認の送信先 Fabrikam を表す|  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-add-reference-to-the-biztalk-edi-application"></a>BizTalk EDI アプリケーションへの参照を追加するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、、**アプリケーション**ノードで、BizTalk アプリケーション 1 などの edi で使用するアプリケーションを右クリックします。 をポイント**追加**、し、[参照] をクリックします。  
  
2. **アプリケーション参照の追加**ダイアログ ボックスで、 **BizTalk EDI アプリケーション**、 をクリックし、 **OK**。  
  
## <a name="next-steps"></a>次の手順  
 作成および」の説明に従って、Inbound_EDI アセンブリを配置する[手順 2。更新し、チュートリアルのソリューションを展開](../core/step-2-update-and-deploy-the-tutorial-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md)