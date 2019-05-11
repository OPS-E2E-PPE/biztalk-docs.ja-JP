---
title: リンクの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10050c28-0944-4073-afd2-54cd6c8d79a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb50ad367a8e1f72de0f567aaeb46ea07a933f22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355314"
---
# <a name="configuring-links"></a>リンクの構成

## <a name="overview"></a>概要
リンクにはプロパティがあり、表示されているグリッド ページでリンクを選択すると、これらのプロパティが [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウに表示されます。 参照リンクに関連付けられているプロパティについては、次を参照してください。**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 

## <a name="source-target-and-label"></a>ソース、ターゲット、およびラベル  
 マップ内のリンクは次のプロパティで構成されます。  
  
- **ソース リンク**します。 使用する、**ソース リンク**プロパティを出力インスタンス メッセージの構築に使用される入力インスタンス メッセージからのデータの性質を構成します。 既定 (最も一般的な選択) では、入力インスタンス メッセージの要素または属性の値が使用されます。 他の選択肢としては、入力インスタンス メッセージの要素または属性の名前の使用などがあります。 このプロパティは、使用可能な選択肢の詳細については、次を参照してください。**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
- **ターゲット リンク**します。 使用する、**ターゲット リンク**プロパティを BizTalk マッパーがノード階層レベルを照合する方法を構成します。 既定では、送信元スキーマの階層がフラット化されて、出力インスタンス メッセージが作成されます。 また階層を維持して、リンクを上から順に一致させるか、下から順に一致させるかを選択することもできます。 このプロパティは、使用可能な選択肢の詳細については、次を参照してください。**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
- **ラベル**します。 使用する、**ラベル**プロパティを既定で使用される XPath 値よりも、リンクのわかりやすい名前を作成します。 このプロパティを構成すると、テーブルドリブン ループの入力としてリンクを使用する場合に特に便利です。 このプロパティは、使用可能な選択肢とテーブルドリブン ループについての詳細については、次を参照してください。**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 参照してください[テーブル ループ functoid およびテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)、それぞれします。  
  
## <a name="see-also"></a>参照  
  [リンクのプロパティを編集する方法](../core/how-to-edit-link-properties.md)