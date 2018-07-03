---
title: '手順 2: 更新し、チュートリアル ソリューションのデプロイ |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d03adfdd-1160-4e8c-a564-3acb2ecd0476
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 714b76ac87b183daa30740268e1a306217d5d13d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998883"
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a>手順 2: 更新し、チュートリアル ソリューションのデプロイ
![手順 2 の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")  
  
 このステップでは、このチュートリアルのために用意されたソリューションを更新し、チュートリアルのアセンブリをビルドして展開します。 このチュートリアルで使用できるように、必要なスキーマ、カスタム送信パイプライン、およびマップは既に作成されています。 マップは、850 の EDI データを注文システムで必要な形式に変換するために使用します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a>EDI 受信処理ソリューションを Visual Studio でビルドできるようにするには  
  
1. 開始**Microsoft Visual Studio**に管理者として。  
  
   > [!CAUTION]
   >  管理者特権を使用して Visual Studio を起動しないと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にソリューションを展開しているときにエラーが表示されます。  
  
2. Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**オープン**、 をクリックし、**プロジェクト/ソリューション**します。 移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer Tutorial 選択**EDI Inbound Processing.sln**、順にクリックします**オープン**します。  
  
   > [!NOTE]
   >  このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。 そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。  
  
3. 右クリックし、 **Inbound_EDI**ソリューション エクスプ ローラーでプロジェクトを選び**プロパティ**します。  
  
4. コンソール ツリーで、 **Inbound_EDI プロパティ ページ**ダイアログ ボックスで、**展開**し、 **Server**フィールドは、コンピューター名が入力されていることを確認します。  
  
5. コンソール ツリーで、クリックして**署名**選び**アセンブリに署名**します。 **厳密なキー名のファイルを選択して**を選択します\<**新規.** \>入力**keyfile.snk**として、**キー ファイル名**します。 クリア**キーファイルをパスワードで保護する**順にクリックします**OK**します。  
  
6. 閉じる、 **Inbound_EDI プロパティ ページ** ダイアログ ボックス。  
  
### <a name="to-deploy-the-project"></a>プロジェクトを展開するには  
  
1. ソリューション エクスプ ローラーで、 **X12_00401_850.xsd**スキーマ。 これが開くことを確認します。  
  
2. ソリューション エクスプ ローラーで、 **Inbound4010850_to_OrderFile.btm**マップします。 これが開くことを確認します。  
  
   > [!NOTE]
   >  プロジェクトの Inbound4010850_to_OrderFile.btm マップにより、受信する 850 のテスト メッセージのデータが、OrderSystem フォルダー (\toOrderSystem) 宛ての送信 XML ファイルにマップされます。  
  
3. ソリューション エクスプ ローラーで右クリックし、 **Inbound_EDI**順に選択して**ビルド**プロジェクトをビルドします。  
  
4. ソリューション エクスプ ローラーで右クリックし、 **Inbound_EDI**順に選択して**デプロイ**プロジェクトを配置します。  
  
5. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、 \< **すべての成果物**\>選び**リソース**します。 いることを確認、 **Inbound_EDI**アセンブリが表示されます。  
  
## <a name="next-steps"></a>次の手順  
 組織のパーティとビジネス プロファイルを構成する (**OrderSystem**)」の説明に従って、[手順 3: 組織のパーティとビジネス プロファイルを構成します。](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
## <a name="see-also"></a>参照  
 [手順 1: EDI インターフェイス開発チュートリアルのための準備](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)