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
ms.openlocfilehash: 273a556cd943d5404a4d5dfe38b1f31e29fd752b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012251"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a>XML 検証ステージ (回復可能なインターチェンジ処理)
**XML validator**パイプライン コンポーネントは、2 つのモードでインターチェンジを処理します。  
  
-   **標準モード**します。 ときに、 **XML validator**標準の検証を実行するコンポーネントが構成されている、トランザクションの作業単位で、インターチェンジに含まれるメッセージを検証します。 特に、インターチェンジのメッセージの検証に失敗した場合、すべてのメッセージを含むインターチェンジ全体が保留キューに配置されます。  
  
-   **回復可能なモード**します。 ときに、 **XML 検証**コンポーネントが構成されているを実行する回復可能なインターチェンジを処理するメッセージの検証が失敗した場合は、メッセージは保留キューに配置されます、 **XML validator**コンポーネントは、インターチェンジの残りのメッセージを検証し続けます。  
  
### <a name="to-configure-recoverable-interchange-processing"></a>回復可能なインターチェンジ処理を構成するには  
  
1. Visual Studio でパイプライン デザイナーを使用して受信パイプラインを開きます。  
  
2. ドラッグ**XML validator**コンポーネントから、**ツールボックス**を**検証**受信パイプラインのステージ。  
  
3. [プロパティ] ウィンドウでの値を設定、**回復可能なインターチェンジ処理**プロパティを**True**する場合は、 **XML validator**コンポーネント プロセス インターチェンジを回復可能なモードでプロパティを設定または**False**コンポーネント、標準モードでインターチェンジを処理する場合。 このプロパティの既定値は`False`します。  
  
   **XMLValidator**に対応するオブジェクト モデル内のクラス、 **XML validator**パイプライン コンポーネント、という名前のパブリック プロパティを持つ**RecoverableInterchangeProcessing**を取得または設定モード プログラムで使用することできます。 ドキュメントを参照して[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)クラスの詳細についてはします。  
  
   検証に成功したメッセージは、親のインターチェンジが到着する受信ポートに対して構成されているパーティに応じて、送信するパーティを確認します。 インターチェンジから抽出されたメッセージでパーティの解決が失敗した場合、パーティの解決は、インターチェンジ全体で失敗したと見なされます。  
  
## <a name="see-also"></a>参照  
 [XML 検証パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-validator-pipeline-component.md)