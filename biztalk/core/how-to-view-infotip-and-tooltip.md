---
title: "ヒントを表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5621bd0a-7028-43fc-b6e8-74a528129285
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06aba645f94b87e0a7951d9c8264056262a12a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-infotip-and-tooltip"></a>ヒントを表示する方法
カーソルをマップ項目の上に移動しポイントすると、その項目についての役に立つ情報が画面ヒントに表示されます。  
  
 BizTalk マッパーでは、ヒントとツールヒントという 2 種類の画面ヒントが使用されます。  
  
-   **ヒント**functoid またはリンクが表示されます。 Functoid またはリンクに対してラベルまたはコメントを構成すると、それらはグリッド ページのヒントとして表示されます。 また、プロパティのテキスト値がの表示を超えた場合、**プロパティ グリッド**、ヒントが表示されます。  
  
-   **ツールヒント**グリッド ビューで現在の配置から部分的または完全に非表示をこれらのスキーマ ノードが表示されます。  
  
 リンク ラベルの場合は、最初の 256 文字だけが保持されて、ツールヒントには完全なラベルが表示されます。 Functoid の場合は、ラベルは最大 256 文字を含むことができ、コメントは 1024 文字に制限されています。 コメントのテキストは、最初の 256 文字だけが表示されるように切り捨てられます。  
  
## <a name="prerequisites"></a>前提条件  
 ツールヒントを表示するには、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-view-the-infotip"></a>ヒントを表示するには  
 マウスを Functoid に移動すると、Functoid の名前、Functoid のラベル、Functoid のコメント、および入力パラメーター (ある場合) についての情報がヒントに表示されます。 **スクリプト**functoid、ヒントには、最初の数行のコードが表示されます。  
  
 リンクのヒントには、次の情報が表示されます。  
  
-   リンク ラベル (設定されている場合)。  
  
-   **: 元接続**です。 送信元接続がスキーマ要素の場合は、要素名が表示されます。 送信元接続が Functoid の場合は、Functoid 名が表示されます。  
  
-   **: 送信先接続**です。 送信先接続がスキーマ要素の場合は、要素名が表示されます。 送信先接続が Functoid の場合は、Functoid 名が表示されます。  
  
 場合内のフィールド、**プロパティ グリッド**フィールドにマウスを移動、ディスプレイを超えるテキストが設定されています。 ヒントにテキスト全体が表示されます。  
  
 次の図は、functoid へのヒント、リンクと**プロパティ グリッド**です。  
  
 ![Functoid、リンク、およびラベルのヒント](../core/media/viewing-infotips.gif "Viewing_infotips")  
  
## <a name="to-view-the-tooltip"></a>ツールヒントを表示するには  
 送信元スキーマまたは送信先スキーマが大きい場合、マップが縦に広がり、スキーマ ノードが部分的に表示されなくなることがあります。 そのような場合は、送信元ノードの上にマウスを移動するとツールヒントが表示されます。  
  
 次の図では、部分的に表示されていない送信先スキーマ ノードのツールヒントを示します。  
  
 ![スキーマ ノードのヒント](../core/media/viewing-tooltips.gif "Viewing_tooltips")  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)