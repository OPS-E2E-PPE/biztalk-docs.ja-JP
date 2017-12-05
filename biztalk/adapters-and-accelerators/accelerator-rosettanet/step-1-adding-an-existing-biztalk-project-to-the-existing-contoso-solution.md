---
title: "手順 1: 既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 343bdf83d90d38a6fc0c626a65353c0185c43f6c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a>手順 1: 既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK には、独自のプライベート プロセスをカスタマイズする際の適切な開始点として機能するプライベート プロセス オーケストレーションが含まれています。 ここでは、ソリューションにこのオーケストレーションを追加し、アセンブリ名を変更して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] インストールでインストールされた PrivateResponder オーケストレーションとの競合を回避します。 開始する前にで作成した Contoso ソリューションを開く[手順 1: Contoso Price and Availability Request の新しい BizTalk ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)です。  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a>PrivateResponder プロジェクトを Contoso ソリューションに追加するには  
  
1.  Contoso ソリューションのフォルダーに PrivateResponder SDK サンプルをコピーします。  
  
    > [!NOTE]
    >  既定では、PrivateResponder SDK サンプルは C:\Program files \microsoft BizTalk に格納\<バージョン\>Accelerator for rosettanet \sdk\privateresponder フォルダーです。  
  
2.  Visual Studio で、[**ファイル**、] をポイント**追加**、クリックして**既存のプロジェクト**です。  
  
3.  既存のプロジェクトの追加 ダイアログ ボックスで、ソリューションのフォルダーに移動、 **PrivateResponder.btproj**プロジェクト ファイル、およびをクリックして**開く**です。  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a>PrivateResponder アセンブリ名および既定の名前空間を変更するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**プロパティ**です。  
  
2.  [PrivateResponder プロパティ ページ] ダイアログ ボックスのコンソール ツリーで、**全般**です。 詳細ウィンドウでの**アセンブリ名**ボックスに、入力**ContosoPriceAndAvailability.PrivateResponder**です。  
  
3.  **Default Namespace**ボックスに、入力**ContosoPriceAndAvailability**です。  
  
4.  をクリックして**OK** PrivateResponder プロパティ ページ ダイアログ ボックスを閉じます。  
  
5.  ソリューション エクスプ ローラーで、 **PrivateResponder.odx**です。  
  
6.  **オーケストレーション**ウィンドウで、いることを確認**オーケストレーションのプロパティ**( **PrivateResponderProcess**) が選択されています。  
  
7.  **プロパティ**ウィンドウで、 **Namespace**フィールドに「 **ContosoPriceAndAvailability**、キーを押します**Enter**です。  
  
## <a name="see-also"></a>参照  
 [手順 2: Contoso 用のボキャブラリの定義と公開](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)