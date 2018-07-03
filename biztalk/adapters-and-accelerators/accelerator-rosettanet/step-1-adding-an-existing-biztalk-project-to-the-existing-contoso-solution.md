---
title: '手順 1: 既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9491c52bfbcbc78e2897cf509b1be320bb223e19
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010243"
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a>手順 1: 既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加
The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK には、独自のプライベート プロセスをカスタマイズする際に、適切な開始点として機能するプライベート プロセス オーケストレーションが含まれています。 ここでは、ソリューションにこのオーケストレーションを追加し、アセンブリ名を変更して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] インストールでインストールされた PrivateResponder オーケストレーションとの競合を回避します。 開始する前で作成した Contoso ソリューションを開きます[手順 1: Contoso Price and Availability Request の新しい BizTalk ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)です。  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a>PrivateResponder プロジェクトを Contoso ソリューションに追加するには  
  
1.  Contoso ソリューションのフォルダーに PrivateResponder SDK サンプルをコピーします。  
  
    > [!NOTE]
    >  既定では、PrivateResponder SDK サンプルは C:\Program files \microsoft BizTalk に格納\<バージョン\>Accelerator for rosettanet \sdk\privateresponder フォルダー。  
  
2.  Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**追加**、 をクリックし、**既存のプロジェクト**します。  
  
3.  既存プロジェクトの追加 ダイアログ ボックスで、ソリューション フォルダーを探します、 **PrivateResponder.btproj**プロジェクト ファイル、およびクリックして**オープン**します。  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a>PrivateResponder アセンブリ名および既定の名前空間を変更するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**プロパティ**します。  
  
2.  [PrivateResponder プロパティ ページ] ダイアログ ボックスのコンソール ツリーで**全般**します。 詳細ペインでの**アセンブリ名**ボックスに「 **ContosoPriceAndAvailability.PrivateResponder**します。  
  
3.  **既定 Namespace**ボックスに「 **ContosoPriceAndAvailability**します。  
  
4.  クリックして**OK** PrivateResponder プロパティ ページ ダイアログ ボックスを閉じます。  
  
5.  ソリューション エクスプ ローラーでダブルクリック**PrivateResponder.odx**します。  
  
6.  **オーケストレーション**ウィンドウで、いることを確認**オーケストレーションのプロパティ**( **PrivateResponderProcess**) が選択されています。  
  
7.  **プロパティ**ウィンドウで、 **Namespace**フィールドに「 **[contosopriceandavailability]**、およびキーを押します **」と入力**します。  
  
## <a name="see-also"></a>参照  
 [手順 2: Contoso 用のボキャブラリの定義と公開](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)