---
title: マップのコンパイル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, compiling
- XSLT, generating
- maps, validating
- BizTalk Mapper, compiling
- BizTalk Mapper, validating
ms.assetid: 967181d6-22a9-4a76-ae45-3317c0c6321b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b02fecc64ae238d19ccacb565519321ce960af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357863"
---
# <a name="compiling-maps"></a>マップのコンパイル
マップを検証するときに、BizTalk マッパーのコンパイラ コンポーネントは、拡張可能なスタイル シート言語変換 (XSLT) スタイル シートを生成します。 これには、送信先スキーマで定義されているインスタンス メッセージの送信元スキーマで定義されたインスタンス メッセージを変換するコンパイル済みのマップが作成されます。 マップをコンパイルすると、構造上のルールと指定されているグリッド ページの変換が適用されます。  
  
 リンクなどの変換は、送信先スキーマのレコードとフィールドが表示されるのと同じ順序で処理されます。 たとえば、BizTalk マッパーが変換先を達したとき**レコード**または**フィールド**ノードとリンクを BizTalk マッパーには、リンクのプロパティがコンパイルされます。 操作のレコードまたはフィールド、送信元スキーマからの単純なコピー値があります。 またはアクションが functoid および複数のレコードとフィールドを使用して複数の計算になる場合があります。  
  
 BizTalk マッパーで警告の生成、**出力**ウィンドウと**タスク一覧**コンパイラが不正な出力が生成される状況が発生したときにウィンドウ。 たとえば、functoid が 1 つの入力パラメーターが必要です、入力パラメーターがない場合は、BizTalk マッパーを生成、警告、**出力**ウィンドウ。 一般に、警告が生成された場合は、運用環境でマップを使用しないでください。  
  
 生成された XSLT スタイル シートへのリンクにも表示されます、**出力**マップが正しくコンパイル時にウィンドウ。  
  
 BizTalk Server では、コンパイル済みのマップを使用して、出力インスタンス メッセージに入力インスタンス メッセージの変換を実行します。  
  
## <a name="see-also"></a>参照  
 [マップのテスト](../core/testing-maps.md)   
 [データ変換の構成](../core/data-transformation-configuration.md)   
 [ノード階層レベルの照合](../core/node-hierarchy-level-matching.md)