---
title: インスタンス メッセージを検証する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6302c6-b56b-4572-aa76-0f4c4599672a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb7d83c8ba847a84a38b2701bb5ca2492559d450
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333180"
---
# <a name="how-to-validate-instance-messages"></a>インスタンス メッセージを検証する方法
スキーマを作成した後は、スキーマの場合は、このようなインスタンス メッセージの適切な表現であることがわかっている既存のインスタンス メッセージを検証することで、作業を確認できます。  
  
 このトピックでは、この検証タスクの詳細な手順を説明します。  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a>インスタンス メッセージをスキーマに対して検証するには  
  
1.  ソリューション エクスプ ローラーで、スキーマを右クリックし をクリックし、**プロパティ**します。  
  
2.  必要に応じて、展開し、[プロパティ] ウィンドウで、**全般**のセクション、**全般**正符号をクリックしてタブ (+) アイコン。  
  
3.  **入力インスタンス ファイル名**プロパティの値フィールド、ファイルの名前を入力するか、省略記号ボタン (**.**) ボタンをクリックして、スキーマに対して検証するインスタンス メッセージを含むファイルを参照する値のフィールドの右端にある**オープン**します。  
  
4.  **ソリューション エクスプ ローラー**スキーマ名を右クリックし、クリックして**インスタンスの検証**です。  
  
5.  [出力] ウィンドウで、結果を表示します。 このウィンドウには、成功とエラー メッセージが表示されます。  
  
> [!NOTE]
>  一部のケースのインスタンスがある特定のスキーマから生成されるメッセージは、その同じスキーマの検証を渡すことができません。 詳細については、このような場合は、次を参照してください。[スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)します。 一般に、生成されたインスタンス メッセージを編集し、シナリオをより現実的に表すようにが含まれているデータを変更します。 この変更されたインスタンス メッセージを使用し、スキーマを検証できます。  
  
## <a name="see-also"></a>参照  
 [スキーマのテスト](../core/testing-schemas.md)   
 [スキーマの検証](../core/schema-validation1.md)   
 [インスタンス メッセージの生成および検証](../core/instance-message-generation-and-validation.md)