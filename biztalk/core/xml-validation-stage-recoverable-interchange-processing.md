---
title: "XML 検証ステージ (回復可能なインターチェンジ処理) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ed00971-d85b-4adb-86c4-c56de7ba7c67
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de8f0225e100053fe6dced8165b7fc800c5e4804
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a>XML 検証ステージ (回復可能なインターチェンジ処理)
**XML 検証**パイプライン コンポーネントは、2 つのモードでインターチェンジを処理します。  
  
-   **標準モード**です。 ときに、 **XML 検証**標準の検証を実行するコンポーネントが構成されて、インターチェンジに含まれているメッセージがトランザクションの作業単位で検証されます。 特に、インターチェンジのメッセージの検証に失敗した場合、すべてのメッセージを含むインターチェンジ全体が保留キューに配置されます。  
  
-   **回復可能なモード**です。 ときに、 **XML 検証**コンポーネントが構成されているを実行する回復可能なインターチェンジを処理するメッセージの検証が失敗した場合、メッセージが保留キューに配置され、 **XML 検証**コンポーネントは、インターチェンジの残りのメッセージの検証を続行します。  
  
### <a name="to-configure-recoverable-interchange-processing"></a>回復可能なインターチェンジ処理を構成するには  
  
1.  Visual Studio でパイプライン デザイナーを使用して受信パイプラインを開きます。  
  
2.  ドラッグ**XML 検証**のコンポーネント、**ツールボックス**を**検証**受信パイプラインのステージ。  
  
3.  [プロパティ] ウィンドウ内の値を設定、**回復可能なインターチェンジ処理**プロパティを**True**する場合は、 **XML 検証**コンポーネント プロセス インターチェンジを回復可能なモードでプロパティを設定または**False**コンポーネント、標準モードでインターチェンジを処理する場合。 このプロパティの既定値は`False`します。  
  
 **XMLValidator**に対応するオブジェクト モデル内のクラス、 **XML 検証**パイプライン コンポーネント、という名前のパブリック プロパティには**RecoverableInterchangeProcessing**を取得または設定モード プログラムで使用することできます。 ドキュメントを参照して[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)詳細情報のクラスです。  
  
 検証に成功したメッセージは、親のインターチェンジが到着する受信ポートに対して構成されているパーティに応じて、送信するパーティを確認します。 インターチェンジから抽出されたメッセージでパーティの解決が失敗した場合、パーティの解決は、インターチェンジ全体で失敗したと見なされます。  
  
## <a name="see-also"></a>参照  
 [XML 検証パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-validator-pipeline-component.md)