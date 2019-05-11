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
ms.openlocfilehash: 2028170edc6cd2e4414172f2be37f3c7da7ebb8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333047"
---
# <a name="how-to-view-infotip-and-tooltip"></a>ヒントとツールヒントを表示する方法
マップ アイテムの上クリックしてしなくても、カーソルを移動すると、その項目に関する有用な情報を画面ヒントが表示されます。  
  
 BizTalk マッパーでは、2 種類の画面ヒント-ヒントとツールヒントを使用します。  
  
- **ヒント**functoid またはリンクが表示されます。 Functoid またはリンクに対してラベルまたはコメントを構成するときに、グリッド ページのヒントとして表示します。 表示を超えたときにも、プロパティのテキスト値、**プロパティ グリッド**ヒントが表示されます。  
  
- **ツールヒント**グリッド ビューで現在の配置から部分的または完全に非表示をこれらのスキーマ ノードが表示されます。  
  
  リンク ラベルの場合は、最初の 256 文字のみが保持される場合と、ツールヒントには、完全なラベルが表示されます。 Functoid の場合、ラベルは最大 256 文字を含めることができ、コメントは 1024 文字に制限されています。 コメントのテキストがコメントのだけ最初の 256 文字を表示するように切り捨てられます。  
  
## <a name="prerequisites"></a>前提条件  
 ツールヒントを表示するには、BizTalk マッパーが実行されているを確認します。  
  
## <a name="to-view-the-infotip"></a>ヒントを表示するには  
 Functoid にマウスを移動すると、ヒントは、(ある場合)、functoid 名、functoid のラベル、functoid のコメント、および入力パラメーターの情報を表示します。 **Scripting** functoid、ヒントには、最初の数行のコードが表示されます。  
  
 リンクをヒントには、次の情報が表示されます。  
  
- 場合、ラベルにリンクを設定します。  
  
- **: 元接続**します。 ソース接続がスキーマ要素の場合は、要素名を示します。 ソース接続が functoid、functoid 名が表示されます。  
  
- **: 送信先接続**します。 転送先接続がスキーマ要素の場合は、要素名を示します。 転送先接続が functoid、functoid 名が表示されます。  
  
  場合のフィールド、**プロパティ グリッド**フィールドにマウスを移動するテキストが、表示を超えています。 ヒントは、完全なテキストで表示されます。  
  
  次の図は、functoid へのヒントを示しています。 リンク、および**プロパティ グリッド**します。  
  
  ![Functoid、リンク、およびラベルのヒント](../core/media/viewing-infotips.gif "Viewing_infotips")  
  
## <a name="to-view-the-tooltip"></a>ツールヒントを表示するには  
 元または送信先スキーマが大きい場合、マップが垂直方向にまたがることができます。そのため、スキーマ ノードが部分的に表示する可能性があります。 このような場合は、送信元ノードの上にマウスを移動するときにツールヒントを表示できます。  
  
 次の図は、部分的に表示されていない送信先スキーマ ノードのヒントを示します。  
  
 ![スキーマ ノードのヒント](../core/media/viewing-tooltips.gif "Viewing_tooltips")  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)