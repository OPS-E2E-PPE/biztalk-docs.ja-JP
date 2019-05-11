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
ms.openlocfilehash: f76e8043519672e5fe5b39bc9ce75b71dc0e95d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380717"
---
# <a name="known-issues-with-schema-generation-and-validation"></a>スキーマの生成と検証に関する既知の問題
このトピックでは、スキーマの生成と検証に関する既知の問題に関する情報を提供します。  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a>タグを持つ位置指定レコードの生成されたインスタンス メッセージが正しくない可能性があります。  
 位置指定レコードのタグはフィールド内であることができますか、フィールドの間にまたがることができます。 いずれの場合も、生成されたインスタンスは無効になります、、解析エンジンで、解析ステージ中にエラーが発生します。  
  
 タグ (子レコードまたはフィールドの子) 子の一部でない場合、この問題は発生しません。  
  
 この問題を回避するには、スキーマの既定値として、タグの実際の値が含まれます。 フラット ファイル拡張機能の BizTalk エディターで設定できます、**固定値**または**既定値**タグの値を持つ適切な位置指定フィールドのプロパティ。  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a>いくつかの制限を持つフィールドに対して生成されたインスタンス メッセージでは、検証を渡すことができません。  
 1 つまたは複数を含むスキーマからインスタンス メッセージを生成すると**フィールド要素**と**フィールド属性**など、制限メカニズムを使用して派生されているデータ型を持つノードときに、**パターン**プロパティを使用すると、このようなフィールドに対して生成されたサンプル データは可能性があります、同じスキーマを使用してそのインスタンス メッセージの検証に成功したことを制限の要件に準拠していませんどの it が生成されました。  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a>無限ループを含むスキーマに対して生成されたインスタンス メッセージは、有効でない可能性があります。  
 持つノードに循環参照が含まれている場合、スキーマが無限ループを含めることができます、 **Min Occurs**本質的には、終了条件を防止、1 つ以上のプロパティの値。 インスタンス メッセージの生成は、生成操作は完了できますが、生成されたインスタンス メッセージが生成されたスキーマに準拠しませんように意図的に終了します。 このようなスキーマは、通常は疑いがあります。  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a>ターゲットの名前空間を持つドキュメント スキーマに対して XML インスタンスの検証に失敗した ="<http://www.w3.org/XML/1998/namespace>"  
 ハイパーリンク"<http://www.w3.org/XML/1998/namespace>"は予約された名前空間のプレフィックスが"XML"にする必要があります。 "XML"プレフィックスを手動で編集することができます。

## <a name="see-also"></a>関連項目
これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
