---
title: 大規模なスキーマの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8348036d-6edb-46a3-badd-0223cfe0a92f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f122d56c5a5632a3d6edcb785968c51f487f0b8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295372"
---
# <a name="working-with-large-schemas"></a>大規模なスキーマの使用
スキーマが非常に大きいになると、XSD ビューの更新がかかり、他のユーザー インターフェイスの応答にも影響できることがあります。 この問題を解決するには自動更新機能をオフにし、代わりに、手動**更新**XSD ビューを定期的に更新する XSD ビューでリンクします。 詳細な手順について有効にするため、自動更新機能をオフの場合、上で XSD ビューの自動更新のオンとオフ"するには」の手順で[XSD ビューの管理](../core/how-to-manage-the-xsd-view.md)します。  
  
 パフォーマンスも低下するサイズの大きいスキーマで複数のルートにアタッチされている、**スキーマ**ノード。 設定、**ルート参照**プロパティは、ユーザー インターフェイスでのパフォーマンスを向上させることがあります。 設定**ルート参照**コンパイラを作成するためのパフォーマンスが向上C#クラスのすべてのスキーマのルートに対して。 単一のルートでは、少数のクラスの作成を意味します。  
  
 **インスタンスの検証**が表示されるユーザー インターフェイスのインスタンスを検証する前に、スキーマの検証が常に行われるため、速度の遅い。 スキーマの検証は、ユーザー インターフェイスでのみ発生します。 設定、**ルート参照**プロパティ ユーザー インターフェイスのパフォーマンスも向上ここでします。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターを使用してください。](../core/using-biztalk-editor.md)