---
title: XML 検証ステージ (回復可能なインターチェンジ処理) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ed00971-d85b-4adb-86c4-c56de7ba7c67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c2aad27b00012972214e2d86ad78a871bb609fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401556"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a>XML 検証ステージ (回復可能なインターチェンジ処理)
**XML validator**パイプライン コンポーネントは、2 つのモードでインターチェンジを処理します。  
  
-   **標準モード**します。 ときに、 **XML validator**標準の検証を実行するコンポーネントが構成されている、トランザクションの作業単位で、インターチェンジに含まれるメッセージを検証します。 具体的には、インターチェンジ内のメッセージの検証が失敗した場合、インターチェンジ全体 (すべてのメッセージを含む) は保留キューに配置されます。  
  
-   **回復可能なモード**します。 ときに、 **XML 検証**コンポーネントが構成されているを実行する回復可能なインターチェンジを処理するメッセージの検証が失敗した場合は、メッセージは保留キューに配置されます、 **XML validator**コンポーネントは、インターチェンジの残りのメッセージを検証し続けます。  
  
### <a name="to-configure-recoverable-interchange-processing"></a>回復可能なインターチェンジ処理を構成するには  
  
1. Visual Studio でパイプライン デザイナーを使用して、受信パイプラインを開きます。  
  
2. ドラッグ**XML validator**コンポーネントから、**ツールボックス**を**検証**受信パイプラインのステージ。  
  
3. [プロパティ] ウィンドウでの値を設定、**回復可能なインターチェンジ処理**プロパティを**True**する場合は、 **XML validator**コンポーネント プロセス インターチェンジを回復可能なモードでプロパティを設定または**False**コンポーネント、標準モードでインターチェンジを処理する場合。 このプロパティの既定値は `False` です。  
  
   **XMLValidator**に対応するオブジェクト モデル内のクラス、 **XML validator**パイプライン コンポーネント、という名前のパブリック プロパティを持つ**RecoverableInterchangeProcessing**を取得または設定モード プログラムで使用することできます。 ドキュメントを参照して[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)クラスの詳細についてはします。  
  
   正常に検証メッセージがある、送信元パーティを親のインターチェンジが到着する受信ポート用に構成されたパーティに応じて確認します。 インターチェンジから抽出されたメッセージのパーティの解決に失敗した場合は、インターチェンジ全体に対する失敗したパーティの解決が考慮します。  
  
## <a name="see-also"></a>参照  
 [XML 検証パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-validator-pipeline-component.md)