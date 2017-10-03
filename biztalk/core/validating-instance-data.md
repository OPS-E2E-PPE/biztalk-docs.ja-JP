---
title: "インスタンス データの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19c3ca83-0abf-42ba-8e29-653ff12d5e20
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86cde9d6133959e34ec09880be8a6beca5c37191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validate-instance-data"></a>インスタンス データを検証します。

## <a name="overview"></a>概要
マップのテストを実行している際に、インスタンス データを送信元および送信先スキーマに照合して検証し、スキーマの構造に準拠していることを確認したい場合があります。 送信元または送信先スキーマに対してインスタンス メッセージを検証するには、ソリューション エクスプ ローラーでスキーマを右クリックし、をクリックして**インスタンスの検証**です。  
  
> [!IMPORTANT]
>  出力でカスタム データまたは定数を使用する場合、送信元のテスト データと送信先の定数値のデータ型が有効であることを確認する必要があります。 マップを検証するときに BizTalk マッパーをチェックしません、インスタンス データに、スキーマによって定義されたすべてのデータ型が違反しているかどうか。 データ型の確認は、マップのテストまたはインスタンス データの検証を行うと実行されます。  
  
 生成し、BizTalk エディターを使用してインスタンス データを検証する方法の詳細については、次を参照してください。[インスタンス メッセージの生成と検証](../core/instance-message-generation-and-validation.md)と[インスタンスの検証](../core/instance-validation.md)です。 のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。 **値**BizTalk がインスタンス データがどのように生成するか、スキーマのノードのプロパティにも影響します。 詳細については、次を参照してください。、**スキーマ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="see-also"></a>参照  
-  [インスタンス メッセージの生成と検証](../core/instance-message-generation-and-validation.md)   
-  [Visual Studio でのスキーマを検証する方法](../core/how-to-validate-schemas-in-visual-studio.md)   
-  **マップ プロパティのリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [マップのテスト](../core/testing-maps.md)