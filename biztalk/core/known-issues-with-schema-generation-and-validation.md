---
title: スキーマの生成と検証に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 298376e0d8e22e84964c2a70df165664f0da9b45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968219"
---
# <a name="known-issues-with-schema-generation-and-validation"></a>スキーマの生成と検証に関する既知の問題
このトピックでは、スキーマの生成と検証に関する既知の問題について説明します。  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a>タグを持つ位置指定レコードの生成されたインスタンス メッセージが正しくない可能性があります。  
 位置指定レコードのタグが、フィールド内に配置されている可能性があります。または、フィールドをまたいでいる可能性があります。 どちらの場合も、生成されたインスタンスは無効で、解析ステージ中に解析エンジンでエラーが発生します。  
  
 タグが子 (子レコードまたは子フィールド) の一部ではない場合、この問題は発生しません。  
  
 この問題を回避するには、タグの実際の値をスキーマの既定値として格納してください。 フラット ファイル拡張機能の BizTalk エディターで設定できます、**固定値**または**既定値**タグの値を持つ適切な位置指定フィールドのプロパティ。  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a>フィールドに対して制限付きで生成されたインスタンス メッセージが検証に合格しない  
 1 つまたは複数を含むスキーマからインスタンス メッセージを生成すると**フィールド要素**と**フィールド属性**など、制限メカニズムを使用して派生されているデータ型を持つノードときに、**パターン**プロパティを使用すると、このようなフィールドに対して生成されたサンプル データは可能性があります、同じスキーマを使用してそのインスタンス メッセージの検証に成功したことを制限の要件に準拠していませんどの it が生成されました。  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a>無限ループを含むスキーマに対して生成されたインスタンス メッセージが無効になる  
 持つノードに循環参照が含まれている場合、スキーマが無限ループを含めることができます、 **Min Occurs**本質的には、終了条件を防止、1 つ以上のプロパティの値。 生成操作を終了するには、インスタンス メッセージの生成を強制終了させます。このため、生成されたインスタンス メッセージは、生成元のスキーマに準拠しません。 通常、このようなスキーマが問題となります。  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a>ターゲットの名前空間を持つドキュメント スキーマに対して XML インスタンスの検証に失敗した ="<http://www.w3.org/XML/1998/namespace>"  
 ハイパーリンク"<http://www.w3.org/XML/1998/namespace>"は予約された名前空間のプレフィックスが"XML"にする必要があります。 このプレフィックスを手動で "XML" に変更できます。

## <a name="see-also"></a>参照
これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
