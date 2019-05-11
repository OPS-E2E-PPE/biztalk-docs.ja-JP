---
title: マップ項目を検索する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.search
ms.assetid: 3dbb089a-6aa8-4921-a82d-81d3a193e933
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66e76b1f13d787c17b25c7659bf37eeeb4126610
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383986"
---
# <a name="how-to-search-for-map-items"></a>マップ項目を検索する方法
BizTalk マッパーを使用すると、送信元スキーマ、送信先スキーマ、およびグリッド画面の項目を検索できます。 このトピックでは、次の操作を実行する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-search-for-items"></a>項目を検索するには  
 検索するスキーマを選択します。 送信元スキーマを選択すると、BizTalk マッパーは送信元スキーマでのみ一致するものを検索します。 ただし、送信元スキーマと送信先スキーマの両方を選択できます。  
  
> [!NOTE]
>  選択内容を確認するには、スキーマまたはスキーマ項目の前にマークを検索します。  
  
 ![マップ項目の検索](../core/media/searching-map-items.gif "Searching_map_items")  
  
 **検索**マッパー ユーティリティ リボンのボックスに検索する項目の名前を入力します。 送信元または送信先スキーマのノードの名前、および Functoid の名前、ラベル、コメント、入力、またはスクリプトで、文字列を検索できます。  
  
 検索文字列を入力すると、検索条件を満たすオブジェクトが強調表示されます。 キーボードでキーを使用するか、矢印、検索結果を走査できるまたは![一覧で上へ移動](../core/media/move-up-button.gif "Move_up_button")と![一覧で下へ移動](../core/media/move-down-button.gif "Move_down_button")ユーティリティ リボンでアイコン。 検索結果が 3 つのビューすべてに存在する場合、検索結果の移動は送信元スキーマ、リレーションシップ ビュー、送信先スキーマの順に行われます。 検索結果を後に、検索文字列を削除するかをクリックして、検索を閉じることができます、(![マッパー検索のクリア](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) 検索文字列の横にあるアイコン。  
  
> [!NOTE]
>  また、Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら J キーを押して、または Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら K キーを押して、検索結果内をそれぞれ上または下に移動できます。 マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
> [!IMPORTANT]
>  リレーションシップ ビューの検索結果を 1 つのマップ ビューで表示できない場合は、他のヒットがある方向に点滅する矢印が表示されます。 上向きの矢印のアイコンなど、(![追加検索結果の双方向](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) をスクロールして表示できる追加の検索結果があることを示します。 同様に、検索結果が別のマップ ページにある場合は、そのページのページ タブが黄色で強調表示されます。 強調表示されたページにマウスを移動すると、ツールヒントにそのページにある一致した検索結果の数が表示されます。 ステータス バーに検索結果が表示されます。  
  
 ![ステータス バー、検索結果を表示する](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)