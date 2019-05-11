---
title: 複数のアセンブリをマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, tracking profiles
- tracking profiles, mapping assemblies
- assemblies, maps
ms.assetid: 136f1943-9643-4551-8b5b-150c4b4bfebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bdd70b7790599255ccd802d7f0e290df763982c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336340"
---
# <a name="how-to-map-multiple-assemblies"></a>複数のアセンブリをマップする方法
BizTalk アプリケーションは、BAM アクティビティを参照するデータ項目が存在する複数のアセンブリで構成できます。 次の手順では、追跡プロファイルを複数のアセンブリをマップする方法を示します。  
  
### <a name="to-map-multiple-assemblies"></a>複数のアセンブリをマップするには  
  
1.  既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。 追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)します。  
  
2.  をクリックして、**イベント ソースの選択**(追跡プロファイル エディターの右側のウィンドウの上にある) ボタンをクリックします。  
  
3.  選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。  
  
4.  オーケストレーションを含むアセンブリをクリックして、オーケストレーションの描画元の親アセンブリの選択、**アセンブリ名**、ボックスの一覧をクリックして**次**します。  
  
5.  内のデータ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**、ボックスの一覧をクリックして**OK**します。  
  
6.  右側のペインで、データ項目を選択し、左側のウィンドウで、アクティビティ内の適切なノードにドラッグします。  
  
7.  手順 2 ~ 6 の他のアセンブリをマップします。  
  
### <a name="to-map-the-second-assembly"></a>2 番目のアセンブリをマップするには  
  
1.  をクリックして、**イベント ソースの選択**します。  
  
2.  選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。  
  
3.  元のオーケストレーションを含むアセンブリをクリックして、オーケストレーションを描画するために、[次へ] の親アセンブリの選択、**アセンブリ名**、ボックスの一覧をクリックして、 **[次へ]** ボタンをクリックします。  
  
4.  内のデータ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**、ボックスの一覧をクリックして**OK**します。  
  
5.  右側のペインで、データ項目を選択し、左側のウィンドウで、アクティビティ内の適切なノードにドラッグします。  
  
## <a name="see-also"></a>参照  
 [イベント ソースにマップする方法](../core/how-to-map-event-sources.md)   
 [追跡プロファイルの作成](../core/creating-tracking-profiles.md)