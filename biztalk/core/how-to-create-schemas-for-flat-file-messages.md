---
title: "フラット ファイル メッセージのスキーマを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48f2747b-7f26-4fb2-a855-523e093f3813
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58583037b8fae945dea07aa8af62e969b96e073f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-schemas-for-flat-file-messages"></a>フラット ファイル メッセージ用スキーマを作成します。

## <a name="overview"></a>概要
」の説明に従って XML メッセージ スキーマの作成後に[XML メッセージ用スキーマの作成](../core/how-to-create-schemas-for-xml-messages.md)を使用して、**スキーマ エディター拡張機能**のプロパティ、**スキーマ**を有効にするノード、フラット ファイル拡張子です。 フラット ファイル拡張機能を有効にすると、スキーマ内の各種ノードに、多数のプロパティが追加されます。 一般に、これらのプロパティは、フラット ファイル形式のビジネス ドキュメントと、XML 形式のビジネス ドキュメント間の変換方法を制御する目的で使用され、対応するプロパティ値は XSD (XML Schema Definition) 言語の注釈としてスキーマ ファイル内に格納されます。 これらのプロパティを適切に使用するためには、多少の学習が必要になります。各プロパティがフラット ファイル形式のどのような側面を定義しているのかを、十分に理解する必要があります。 

概念では、フラット ファイルのプロパティに関する情報を参照しを参照してください[に関する考慮事項とフラット ファイル メッセージ スキーマの作成](../core/considerations-when-creating-flat-file-message-schemas.md)と**フラット ファイル スキーマの補足のノード プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
## <a name="see-also"></a>参照  
-  [プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md)
-  これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]