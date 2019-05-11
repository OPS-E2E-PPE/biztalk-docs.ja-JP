---
title: マップのリンク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Looping
- Looping functoids
- maps, links
- BizTalk Mapper, links
ms.assetid: 3db77b8d-7b86-4c00-99a0-0513aff9b56b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba3da2b4bebcb559616aa583fd24fd183fd085c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329653"
---
# <a name="links-in-maps"></a>マップのリンク
リンクは、要素または属性は、入力インスタンス メッセージ内のデータ要素または属性の出力インスタンスにコピーの基本的な機能を指定します。 デザイン時に、元と送信先スキーマのレコードとフィールド間のリンクを作成します。 これは、ドライブの作成、送信元スキーマに準拠している入力インスタンス メッセージから送信先スキーマに準拠した出力インスタンス メッセージの実行時にします。  
  
 BizTalk マッパーでは、1 対 1 のリンクと一対多のリンクをサポートします。 たとえば、リンクに接続できます 1 つのレコードまたはフィールド、送信元スキーマから 1 つのレコードまたはフィールドを送信先スキーマの。 リンク接続もできます、1 つのレコードまたはフィールド、送信元スキーマから複数のレコードまたはフィールドを送信先スキーマに。  
  
 リンクにも接続できます複数のレコードまたはフィールド、送信元スキーマから functoid、単一 (または複数) のレコードまたは送信先スキーマのフィールドに接続します。 一般に、複数のソース レコードからリンクを直接または 1 つの宛先のレコードまたはフィールドにフィールドが有効でないし、警告が生成されます。 1 つの例外は、**ループ**functoid。 詳細については、**ループ**functoid を参照してください[ループ Functoid](../core/looping-functoid.md)します。  
  
 このセクションのトピックでは、BizTalk マッパーにおけるリンクの作成と操作に関連する概念について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [リンクの種類](../core/types-of-links.md)  
  
-   [リンクを作成します。](../core/creating-links.md)  
  
-   [リンクを構成します。](../core/configuring-links.md)  
  
-   [レコード間のリンク](../core/record-to-record-linking.md)  
  
-   [anyElement ノードおよび anyAttribute ノード間のリンク](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [コンパイラ ディレクティブおよびリンク](../core/compiler-directives-and-links.md)