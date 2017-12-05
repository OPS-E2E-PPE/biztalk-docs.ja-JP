---
title: "手順 2: 更新し、チュートリアルのソリューションを展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d03adfdd-1160-4e8c-a564-3acb2ecd0476
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67fd3d34f25dd409121a3a21c9eb419b4aadce6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a>手順 2: 更新し、チュートリアルのソリューションを展開
![手順 2 の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")  
  
 このステップでは、このチュートリアルのために用意されたソリューションを更新し、チュートリアルのアセンブリをビルドして展開します。 このチュートリアルで使用できるように、必要なスキーマ、カスタム送信パイプライン、およびマップは既に作成されています。 マップは、850 の EDI データを注文システムで必要な形式に変換するために使用します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a>EDI 受信処理ソリューションを Visual Studio でビルドできるようにするには  
  
1.  開始**Microsoft Visual Studio**を管理者として。  
  
    > [!CAUTION]
    >  管理者特権を使用して Visual Studio を起動しないと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にソリューションを展開しているときにエラーが表示されます。  
  
2.  Visual Studio で、[**ファイル**、] をポイント**開く**、順にクリック**プロジェクト/ソリューション**です。 移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer Tutorial、select **EDI Inbound Processing.sln**、順にクリック**開く**です。  
  
    > [!NOTE]
    >  このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。 いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。  
  
3.  右クリックし、 **Inbound_EDI**ソリューション エクスプ ローラーでプロジェクトをクリックし **プロパティ**です。  
  
4.  コンソール ツリーで、 **Inbound_EDI プロパティ ページ**ダイアログ ボックスで、**展開**し、、**サーバー**フィールドでは、コンピューター名を入力することを確認してください。  
  
5.  コンソール ツリーでクリックして**署名**し、**アセンブリに署名**です。 **強力なキー名ファイルを選択して** \<**新規しています.** \>入力と**keyfile.snk**として、**キー ファイル名**です。 クリア**キーファイルをパスワードで保護する**順にクリック**OK**です。  
  
6.  閉じる、 **Inbound_EDI プロパティ ページ** ダイアログ ボックス。  
  
### <a name="to-deploy-the-project"></a>プロジェクトを展開するには  
  
1.  ソリューション エクスプ ローラーで、 **X12_00401_850.xsd**スキーマです。 これが開くことを確認します。  
  
2.  ソリューション エクスプ ローラーで、 **Inbound4010850_to_OrderFile.btm**マップします。 これが開くことを確認します。  
  
    > [!NOTE]
    >  プロジェクトの Inbound4010850_to_OrderFile.btm マップにより、受信する 850 のテスト メッセージのデータが、OrderSystem フォルダー (\toOrderSystem) 宛ての送信 XML ファイルにマップされます。  
  
3.  ソリューション エクスプ ローラーで右クリックし、 **Inbound_EDI**プロジェクトを選択**ビルド**プロジェクトをビルドします。  
  
4.  ソリューション エクスプ ローラーで右クリックし、 **Inbound_EDI**プロジェクトを選択**展開**プロジェクトを配置します。  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、 \< **すべての成果物**\>し、**リソース**です。 いることを確認、 **Inbound_EDI**アセンブリが一覧表示します。  
  
## <a name="next-steps"></a>次の手順  
 組織のパーティとビジネス プロファイルを構成する (**OrderSystem**)」の説明に従って、[手順 3: 組織のパーティとビジネス プロファイルを構成します。](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
## <a name="see-also"></a>参照  
 [手順 1: EDI インターフェイス開発チュートリアルのための準備](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)