---
title: 複数のアセンブリをマップする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 20a55b6e88889ccfa36adcac11fe548ab1b25bc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254354"
---
# <a name="how-to-map-multiple-assemblies"></a>複数のアセンブリをマップする方法
BizTalk アプリケーションを複数のアセンブリから構成し、それらのアセンブリに BAM アクティビティで参照するデータ項目を格納することができます。 追跡プロファイルに複数のアセンブリをマップするには、次の操作を行います。  
  
### <a name="to-map-multiple-assemblies"></a>複数のアセンブリをマップするには  
  
1.  既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。 追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)です。  
  
2.  クリックして、**イベント ソースの選択**(追跡プロファイル エディターの右側のペインの上にある) ボタンをクリックします。  
  
3.  選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。  
  
4.  オーケストレーションを含むアセンブリをクリックして、オーケストレーションの描画元の親アセンブリの選択、**アセンブリ名**ボックスの一覧し、をクリックして**次**です。  
  
5.  データ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**ボックスの一覧し、をクリックして**OK**です。  
  
6.  右ペインでデータ項目を選択し、左ペインにあるアクティビティの適切なノードにドラッグします。  
  
7.  手順 2. ～ 6. を繰り返し、他のアセンブリをマップします。  
  
### <a name="to-map-the-second-assembly"></a>2 番目のアセンブリをマップするには  
  
1.  クリックして、**イベント ソースの選択**です。  
  
2.  選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。  
  
3.  オーケストレーションを含むアセンブリをクリックして、オーケストレーションの描画元の親アセンブリの [次へ] を選択、**アセンブリ名**ボックスの一覧し、をクリックして、**次**ボタンをクリックします。  
  
4.  データ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**ボックスの一覧し、をクリックして**OK**です。  
  
5.  右ペインでデータ項目を選択し、左ペインにあるアクティビティの適切なノードにドラッグします。  
  
## <a name="see-also"></a>参照  
 [イベント ソースにマップする方法](../core/how-to-map-event-sources.md)   
 [追跡プロファイルを作成します。](../core/creating-tracking-profiles.md)