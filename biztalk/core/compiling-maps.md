---
title: "マップのコンパイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, compiling
- XSLT, generating
- maps, validating
- BizTalk Mapper, compiling
- BizTalk Mapper, validating
ms.assetid: 967181d6-22a9-4a76-ae45-3317c0c6321b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346769519343afe9456a7b1e7cf9a3bd5bb159ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="compiling-maps"></a>マップのコンパイル
マップを検証すると、BizTalk マッパーのコンパイラ コンポーネントが XSLT (Extensible Stylesheet Language Transformations) スタイルシートを生成します。 これにより、送信元スキーマによって定義されるインスタンス メッセージを送信先スキーマによって定義されるインスタンス メッセージに変換するコンパイル済みのマップが作成されます。 マップをコンパイルすると、構造上のルールが検証され、グリッド ページで指定されている変換が実行されます。  
  
 リンクなどの変換は、送信先スキーマのレコードとフィールドの表示順に処理されます。 たとえば、BizTalk マッパーが変換先を達したとき**レコード**または**フィールド**リンクでは、BizTalk マッパーでノードが、リンクのプロパティをコンパイルします。 アクションは、送信元スキーマのレコードまたはフィールドからの単純なコピー値になります。また、Functoid および複数のレコードとフィールドを使用した、さまざまな計算になる場合もあります。  
  
 BizTalk マッパーで警告の生成、**出力**ウィンドウと**タスク一覧**コンパイラが不正な出力が生成される状況を検出したときにウィンドウです。 たとえば、functoid が 1 つの入力パラメーターが必要です、入力パラメーターがない場合は、BizTalk マッパーに警告を生成、**出力**ウィンドウです。 一般的に、警告が生成された場合は、実稼働環境でそのマップを使用しないでください。  
  
 生成された XSLT スタイル シートへのリンクにも表示されます、**出力**マップが正しくコンパイルするときにウィンドウです。  
  
 BizTalk Server は、コンパイル済みのマップを使用して、入力インスタンス メッセージを出力インスタンス メッセージに変換します。  
  
## <a name="see-also"></a>参照  
 [マップのテスト](../core/testing-maps.md)   
 [データ変換の構成](../core/data-transformation-configuration.md)   
 [ノード階層レベルの照合](../core/node-hierarchy-level-matching.md)