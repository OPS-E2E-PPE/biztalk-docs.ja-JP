---
title: リンクの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compiler directives, links
- elastic links [maps]
- maps, links
- BizTalk Mapper, links
- partial links [maps]
- fixed links [maps]
ms.assetid: 348fae77-2e25-4b79-93bb-d42f3d18a3f7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aacaf93ce41d60d414145fbfaf19f95551da4a77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396613"
---
# <a name="types-of-links"></a>リンクの種類
次の一覧は、BizTalk マッパーで使用できるさまざまな種類のリンクを示しています。  
  
- **柔軟なリンク。** "柔軟な" という用語は、リンクの両端が接続される前の、作成中のリンクに適用されます。 たとえば、送信元スキーマのフィールドからのリンクをドラッグして、送信先スキーマに対応するフィールドにまだ接続がない場合は、リンクがエラスティック。 接続を完了すると、柔軟なリンクが固定リンクになります。  
  
   リンクの 1 つのエンドポイントを、別のノードまたは Functoid にドラッグできます。 リンクの配置の詳細については、次を参照してください。[リンクを作成する方法](../core/how-to-create-links.md)します。  
  
- **固定リンク。** "固定" という用語は、送信元インスタンス メッセージから送信先インスタンス メッセージへの値の移動 (または、移動の一部) を表すために明示的に構築されたリンクに適用されます。 直接接続する固定リンク、**レコード**または**フィールド**ソース スキーマのノードに、**レコード**または**フィールド**マップ先のノードスキーマでは、実行時にデータの直線コピーを表します。 一方の端を Functoid に接続している固定リンクは、実行時の入力インスタンス メッセージから出力インスタンス メッセージへのデータの移動の一部を表します。 これらを組み合わせて送信元スキーマと送信先スキーマのリンクを確立すると、データのアイテム全体の移動が示されます。  
  
- **部分的なリンク。** 部分的な語句が対象の現在表示できない、正確なリンクに適用されます**レコード**または**フィールド**ノードの送信元または送信先スキーマで接続されています。 これが発生したときに、**レコード**または**フィールド**スキーマのツリー表記でいずれかの先祖ノードが折りたたまれているために、アタッチ先のノードは表示されません。 部分的なリンクの詳細については、次を参照してください。[リンクの表示を最適化する方法](../core/how-to-optimize-the-display-of-links.md)します。  
  
- **コンパイラ リンクを示します。** "コンパイラ" という用語は、BizTalk プロジェクトを作成する際に BizTalk マッパーが自動的に作成するリンクに適用されます。 たとえば、テーブルドリブン ループを構成すると、コンパイラ リンクは、送信元スキーマのレコードおよびフィールドと送信先スキーマのレコードおよびフィールドとの関係およびリンクを示します。 このようなリンクは、コンパイラ ディレクティブで自動的に生成させることができます。また、ユーザーがリンクを生成することもできます。  
  
  既定で、BizTalk マッパーは、マップの詳細を区別するためにさまざまな色付きの線を使用して、これらの各種のリンクを表示します。 これらのさまざまな種類のリンクを使用する色を変更することができます、**オプション**コマンドを**ツール**メニュー。 色の変化が異なるカテゴリのリンクを表示する方法の詳細については、次を参照してください。[方法、色のカスタマイズ、BizTalk マッパーでフォント](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)します。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードとフィールド マッピングを指定する](../core/using-links-to-specify-record-and-field-mappings.md)