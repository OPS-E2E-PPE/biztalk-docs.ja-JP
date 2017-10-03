---
title: "インスタンス メッセージを検証する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f6302c6-b56b-4572-aa76-0f4c4599672a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd0baa898f801c924cffc5a446aa1a22d063a8fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-validate-instance-messages"></a>インスタンス メッセージを検証する方法
作成したスキーマが正しく構築されているかどうかは、そのスキーマに対して適切な表記になっていることが確認されている、既存のインスタンス メッセージを検証することによってチェックできます。  
  
 このトピックでは、この検証作業を行うための手順について説明します。  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a>スキーマを使ってインスタンス メッセージを検証するには  
  
1.  ソリューション エクスプ ローラーで、スキーマを右クリックし、をクリックして**プロパティ**です。  
  
2.  必要に応じて、プロパティ ウィンドウで、展開、**全般**のセクション、**全般**の正符号をクリックしてタブ (+) アイコン。  
  
3.  **入力インスタンス ファイル名**プロパティの値フィールド、ファイルの名前を入力するか、省略記号ボタン (**.**) ボタンをクリックして、スキーマに対して検証するインスタンス メッセージを含むファイルを参照するフィールドの右端にある**開く**です。  
  
4.  **ソリューション エクスプ ローラー**スキーマ名を右クリックし、クリックして**インスタンスの検証**です。  
  
5.  出力ウィンドウに結果が表示されます。 このウィンドウには、成功とエラーのメッセージが表示されます。  
  
> [!NOTE]
>  特定のスキーマから生成されたインスタンス メッセージが、同じスキーマを使った検証に合格しない場合があります。 このような場合の詳細については、次を参照してください。[に関する既知の問題のスキーマの生成と検証](../core/known-issues-with-schema-generation-and-validation.md)です。 通常、インスタンス メッセージを生成した後は、実際のシナリオに合わせて修正し、データを変更します。 インスタンス メッセージを修正してから、スキーマを検証してください。  
  
## <a name="see-also"></a>参照  
 [スキーマのテスト](../core/testing-schemas.md)   
 [スキーマの検証](../core/schema-validation1.md)   
 [インスタンス メッセージの生成と検証](../core/instance-message-generation-and-validation.md)