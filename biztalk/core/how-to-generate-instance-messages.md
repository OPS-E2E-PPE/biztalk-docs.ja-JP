---
title: インスタンス メッセージを生成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff74c67a-7e73-4153-9ec4-e6e50464ee92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f851a2888fe0dd9a82b86a47d2ca8faa42c8edf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385040"
---
# <a name="how-to-generate-instance-messages"></a>インスタンス メッセージを生成する方法
スキーマを作成した後、動作を確認する方法の 1 つでは、スキーマからサンプル インスタンス メッセージを生成します。 多くの点で、インスタンス メッセージを見てはスキーマ ツリーまたはスキーマの XML スキーマ定義 (XSD) 言語表記のいずれかを調べるよりもはるかに簡単です。 これに対応するインスタンス メッセージのバリエーションを記述する必要があるスキーマとだけが、スキーマで指定された形式を使用して一部のデータを伝達するために必要な特定のインスタンス メッセージであるためにです。 生成されたインスタンス メッセージ サンプルであり、対応するスキーマによって定義された構造体のすべてを表示しない場合があります。  
  
### <a name="to-explicitly-specify-a-file-to-contain-the-generated-instance-message"></a>生成されたインスタンス メッセージを格納するファイルを明示的に指定するには  
  
1.  ソリューション エクスプ ローラーで右クリックして、インスタンス メッセージを生成するスキーマ**プロパティ**します。  
  
2.  必要に応じて、展開し、[プロパティ] ウィンドウで、**全般**のセクション、**全般**正符号をクリックしてタブ (+) アイコン。  
  
3.  **出力インスタンス ファイル名**プロパティの値フィールド、ファイルの名前を入力するか、省略記号ボタン (**.**) 生成されたインスタンス メッセージに、配置をクリックしてのファイルを参照する値のフィールドの右端にあるボタン**保存**します。  
  
### <a name="to-specify-the-type-of-the-generated-instance-message"></a>生成されたインスタンス メッセージの種類を指定するには  
  
1.  ソリューション エクスプ ローラーで右クリックして、インスタンス メッセージを生成するスキーマ**プロパティ**します。  
  
2.  必要に応じて、展開し、[プロパティ] ウィンドウで、**全般**のセクション、**全般**正符号をクリックしてタブ (+) アイコン。  
  
3.  **インスタンスの出力の種類の生成**プロパティ値フィールドで、いずれかを選択リストをドロップダウン リストを使って**XML**または**ネイティブ**を生成するインスタンス メッセージの種類として。  
  
     **XML**は既定値です。  
  
### <a name="to-generate-a-sample-instance-message-for-a-schema"></a>スキーマのサンプル インスタンス メッセージを生成するには  
  
1.  ソリューション エクスプ ローラーで右クリックして、インスタンス メッセージを生成するスキーマ**インスタンスの生成**します。  
  
2.  [出力] ウィンドウで、結果を表示します。 このウィンドウには、成功とエラー メッセージが表示されます。  
  
> [!NOTE]
>  出力ウィンドウおよびタスク一覧 ウィンドウがないを開きに関する情報を表示場合は、インスタンスの生成が成功したかが失敗したことがそれらを手動で開くかどうか。 これらのウィンドウの管理に関する詳細については、次を参照してください。[その他の Visual Studio Windows の管理](../core/how-to-manage-other-visual-studio-windows.md)します。  
  
> [!NOTE]
>  値を指定しない場合、**ルート参照**プロパティを BizTalk エディターでは、スキーマの最初のルート ノードのサンプル インスタンス メッセージが生成されます。 値を指定する場合、**ルート参照**プロパティを BizTalk エディターには、そのルートのサンプル インスタンス メッセージが生成されます。  
  
> [!NOTE]
>  一部のケースのインスタンスがある特定のスキーマから生成されるメッセージは、その同じスキーマの検証を渡すことができません。 詳細については、このような場合は、次を参照してください。[スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)します。 一般に、生成されたインスタンス メッセージを編集し、データが含まれているためより現実的なシナリオを表しますを変更します。 この変更されたインスタンス メッセージを使用し、スキーマを検証できます。  
  
## <a name="see-also"></a>参照  
 [スキーマのテスト](../core/testing-schemas.md)   
 [スキーマの検証](../core/schema-validation1.md)   
 [インスタンス メッセージの生成および検証](../core/instance-message-generation-and-validation.md)