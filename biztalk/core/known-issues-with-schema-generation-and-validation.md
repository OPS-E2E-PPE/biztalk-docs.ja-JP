---
title: "スキーマの生成と検証に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a462ab04aad857bf87b189cafce14bb9c3747e8
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="known-issues-with-schema-generation-and-validation"></a>スキーマの生成と検証に関する既知の問題
このトピックでは、スキーマの生成と検証に関する既知の問題について説明します。  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a>タグが位置指定レコードの生成されたインスタンス メッセージが正しくない可能性があります。  
 位置指定レコードのタグが、フィールド内に配置されている可能性があります。または、フィールドをまたいでいる可能性があります。 どちらの場合も、生成されたインスタンスは無効で、解析ステージ中に解析エンジンでエラーが発生します。  
  
 タグが子 (子レコードまたは子フィールド) の一部ではない場合、この問題は発生しません。  
  
 この問題を回避するには、タグの実際の値をスキーマの既定値として格納してください。 BizTalk エディターのフラット ファイル拡張子で設定できます、**固定値**または**既定値**タグの値は、適切な位置指定フィールドのプロパティです。  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a>フィールドに対して制限付きで生成されたインスタンス メッセージが検証に合格しない  
 1 つまたは複数を含むスキーマからインスタンス メッセージを生成すると**フィールド要素**と**フィールド属性**などの制約メカニズムを使用して作成されたデータ型を持つノードときに、**パターン**プロパティを使用して、このようなフィールドに対して生成されたサンプル データが同じスキーマを使用してインスタンス メッセージの検証が成功したように、制限の要件に準拠していませんそこが生成されました。  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a>無限ループを含むスキーマに対して生成されたインスタンス メッセージが無効になる  
 持つノードに循環参照が含まれている場合に、スキーマが、無限ループを含めることができます、 **Min Occurs**本質的には、終了条件を防止、1 つ以上のプロパティの値。 生成操作を終了するには、インスタンス メッセージの生成を強制終了させます。このため、生成されたインスタンス メッセージは、生成元のスキーマに準拠しません。 通常、このようなスキーマが問題となります。  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a>ドキュメント スキーマのターゲットの名前空間が "http://www.w3.org/XML/1998/namespace" である場合、XML インスタンスの検証が失敗する  
 ハイパーリンク"http://www.w3.org/XML/1998/namespace" は、予約された名前空間のプレフィックスを持つが"XML"にする必要があります。 このプレフィックスを手動で "XML" に変更できます。

## <a name="see-also"></a>参照
これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
