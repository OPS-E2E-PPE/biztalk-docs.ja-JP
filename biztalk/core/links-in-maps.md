---
title: "マップ内のリンク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoid types, Looping
- Looping functoids
- maps, links
- BizTalk Mapper, links
ms.assetid: 3db77b8d-7b86-4c00-99a0-0513aff9b56b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a32d2a9ef07cf2d79037d7983e49b26c6cfe5e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="links-in-maps"></a>マップのリンク
リンクを使用して、入力インスタンス メッセージの要素や属性のデータを、出力インスタンスの要素や属性にコピーするときの基本的な機能を指定します。 送信元スキーマと送信先スキーマのレコード間およびフィールド間のリンクをデザイン時に作成しておくと、 実行時には、送信元スキーマに準拠した入力インスタンス メッセージから、送信先スキーマに準拠した出力インスタンス メッセージが作成されます。  
  
 BizTalk マッパーは、1 対 1 および 1 対多のリンクをサポートしています。 たとえば、送信元スキーマの単一のレコードまたはフィールドを、送信先スキーマの単一のレコードまたはフィールドに接続するようなリンクを作成する以外に、 送信元スキーマの単一のレコードまたはフィールドを、送信先スキーマの複数のレコードまたはフィールドに接続するようなリンクを作成することもできます。  
  
 送信元スキーマの複数のレコードまたはフィールドを Functoid に接続し、そこから、さらに、送信先スキーマの単一 (または複数) のレコードまたはフィールドに接続するようなリンクを作成することも可能です。 通常は、複数の送信元レコードまたはフィールドを、単一の送信先レコードまたはフィールドに直接接続することはできません。このような多対 1 のリンクでは警告が発生します。 1 つの例外は、**ループ**functoid です。 詳細については、**ループ**functoid を参照してください[ループ Functoid の](../core/looping-functoid.md)します。  
  
 このセクションの各トピックでは、BizTalk マッパーにおけるリンクの作成と使用に関連した概要が説明されています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [リンクの種類](../core/types-of-links.md)  
  
-   [リンクを作成します。](../core/creating-links.md)  
  
-   [リンクを構成します。](../core/configuring-links.md)  
  
-   [レコードへのリンク](../core/record-to-record-linking.md)  
  
-   [リンクから、すべての要素および anyAttribute ノード](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [コンパイラ ディレクティブおよびリンク](../core/compiler-directives-and-links.md)