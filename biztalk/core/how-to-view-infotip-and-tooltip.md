---
title: ヒントとツールヒントを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5621bd0a-7028-43fc-b6e8-74a528129285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 833fedbcb731971bb305c759b6f87a5a575f58e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995939"
---
# <a name="how-to-view-infotip-and-tooltip"></a>ヒントを表示する方法
カーソルをマップ項目の上に移動しポイントすると、その項目についての役に立つ情報が画面ヒントに表示されます。  
  
 BizTalk マッパーでは、ヒントとツールヒントという 2 種類の画面ヒントが使用されます。  
  
- **ヒント**functoid またはリンクが表示されます。 Functoid またはリンクに対してラベルまたはコメントを構成すると、それらはグリッド ページのヒントとして表示されます。 表示を超えたときにも、プロパティのテキスト値、**プロパティ グリッド**ヒントが表示されます。  
  
- **ツールヒント**グリッド ビューで現在の配置から部分的または完全に非表示をこれらのスキーマ ノードが表示されます。  
  
  リンク ラベルの場合は、最初の 256 文字だけが保持されて、ツールヒントには完全なラベルが表示されます。 Functoid の場合は、ラベルは最大 256 文字を含むことができ、コメントは 1024 文字に制限されています。 コメントのテキストは、最初の 256 文字だけが表示されるように切り捨てられます。  
  
## <a name="prerequisites"></a>前提条件  
 ツールヒントを表示するには、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-view-the-infotip"></a>ヒントを表示するには  
 マウスを Functoid に移動すると、Functoid の名前、Functoid のラベル、Functoid のコメント、および入力パラメーター (ある場合) についての情報がヒントに表示されます。 **Scripting** functoid、ヒントには、最初の数行のコードが表示されます。  
  
 リンクのヒントには、次の情報が表示されます。  
  
- リンク ラベル (設定されている場合)。  
  
- **: 元接続**します。 送信元接続がスキーマ要素の場合は、要素名が表示されます。 送信元接続が Functoid の場合は、Functoid 名が表示されます。  
  
- **: 送信先接続**します。 送信先接続がスキーマ要素の場合は、要素名が表示されます。 送信先接続が Functoid の場合は、Functoid 名が表示されます。  
  
  場合のフィールド、**プロパティ グリッド**フィールドにマウスを移動するテキストが、表示を超えています。 ヒントにテキスト全体が表示されます。  
  
  次の図は、functoid へのヒントを示しています。 リンク、および**プロパティ グリッド**します。  
  
  ![Functoid、リンク、およびラベルのヒント](../core/media/viewing-infotips.gif "Viewing_infotips")  
  
## <a name="to-view-the-tooltip"></a>ツールヒントを表示するには  
 送信元スキーマまたは送信先スキーマが大きい場合、マップが縦に広がり、スキーマ ノードが部分的に表示されなくなることがあります。 そのような場合は、送信元ノードの上にマウスを移動するとツールヒントが表示されます。  
  
 次の図では、部分的に表示されていない送信先スキーマ ノードのツールヒントを示します。  
  
 ![スキーマ ノードのヒント](../core/media/viewing-tooltips.gif "Viewing_tooltips")  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)