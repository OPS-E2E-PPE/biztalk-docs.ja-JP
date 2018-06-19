---
title: パイプライン コンポーネントのプロパティを読み取る方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 19a6ccbcbe7588a0a75b4dbe6bf821a19fab965c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254786"
---
# <a name="how-to-read-pipeline-component-properties"></a>パイプライン コンポーネントのプロパティを読み取る方法
[プロパティ] ウィンドウには、コンポーネントの 2 つのセクションが含まれています: [全般] プロパティとコンポーネントのプロパティです。 全般プロパティはすべてのコンポーネントで共通のプロパティですが、値はコンポーネントごとに異なります。  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a>パイプライン コンポーネントの全般プロパティを読み取るには  
  
1.  パイプライン コンポーネントをパイプラインのステージにドラッグします。コンポーネントが既にパイプラインに存在する場合は、コンポーネントを選択します。  
  
2.  [プロパティ] ウィンドウでの**全般**セクションで、次の操作です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|コンポーネントの名前が表示されます。|  
    |**アセンブリ**|アセンブリと、コンポーネントに関連付けられた .NET 情報が表示されます。|  
    |**Description**|パイプライン コンポーネントのフレンドリ名が表示されます。|  
    |**管理されています。**|パイプライン コンポーネントがマネージ型かどうかを示します。 **[はい]** コンポーネントが .NET マネージ コンポーネント以外の場合**いいえ**パイプライン コンポーネントが COM コンポーネントである場合。|  
    |**[パス]**|.NET コンポーネントの完全修飾パスが表示されます。|  
    |**型**|コンポーネントの種類、アセンブリ、およびコンポーネントに関連付けられた .NET 情報が表示されます。|  
  
## <a name="see-also"></a>参照  
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン デザイナーでパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)