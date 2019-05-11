---
title: パイプライン コンポーネントのプロパティを読み取る方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, properties
ms.assetid: 10b1c59c-7ba4-453f-9aaa-1ce9ecf31fac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9a91edb33167ca97ea73949c8419d1df1521ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335685"
---
# <a name="how-to-read-pipeline-component-properties"></a>パイプライン コンポーネントのプロパティを読み取る方法
[プロパティ] ウィンドウには、コンポーネントの 2 つのセクションが含まれています: [全般] プロパティとコンポーネントのプロパティ。 [全般] プロパティは、コンポーネント間の値を変更する場合に、すべてのコンポーネントに共通です。  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a>パイプライン コンポーネントの [全般] プロパティを読み取る  
  
1.  パイプライン コンポーネントをパイプラインのステージにドラッグするか、パイプライン内に既に存在する場合にコンポーネントを選択します。  
  
2.  [プロパティ] ウィンドウでの**全般**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|コンポーネント名を示します。|  
    |**アセンブリ**|アセンブリと、コンポーネントに関連付けられた .NET 情報を示します。|  
    |**[説明]**|パイプライン コンポーネントのフレンドリ名を示します。|  
    |**管理されています。**|パイプライン コンポーネントが管理されているかどうかを示します。 **[はい]** コンポーネントが .NET のマネージ コンポーネント以外の場合**いいえ**パイプライン コンポーネントが COM コンポーネントである場合。|  
    |**[パス]**|.NET コンポーネントに完全修飾パスを示します。|  
    |**型**|コンポーネントの種類、アセンブリ、およびコンポーネントに関連付けられた .NET 情報を示します。|  
  
## <a name="see-also"></a>参照  
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン デザイナーでのパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)