---
title: マップのトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32e2eb52-6740-4cf5-82ec-3b6d0b784276
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bb7b3dc8356172989c215dc13e5fd82e46f4689
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974616"
---
# <a name="troubleshooting-maps"></a>マップのトラブルシューティング
このトピックでは、マップに関するトラブルシューティングの方針、問題の詳細、および対処方法について説明します。  
  
## <a name="troubleshooting-strategies"></a>トラブルシューティングの方針  
  
### <a name="validate-your-map"></a>マップの有効性を検証する  
 当然のことですが、開発中は常に、さまざまな観点からマップの有効性を検証する必要があります。 デザイン、ロジック、スキーマに関する問題点を開発の初期段階で明らかにしておけば、修正が容易であり、別の解決方法を試してみることもできます。  
  
##### <a name="to-validate-a-biztalk-map"></a>BizTalk マップを検証するには  
  
1.  ソリューション エクスプローラーで、検証するマップを開きます。  
  
2.  ソリューション エクスプ ローラーで、マップを右クリックし、をクリックして**マップの検証**です。  
  
3.  [出力] ウィンドウで、結果を検証します。  
  
> [!NOTE]
>  マップの検証時には、テスト インスタンス データが、スキーマで定義されているデータ型に違反しているかどうかはチェックされません。 BizTalk エディターでマップのテストまたはインスタンス データの検証を行うときに、インスタンス データをチェックできます。  
  
### <a name="review-the-xslt-generated-for-your-map"></a>マップに基づいて生成された XSLT を確認する  
 マップ コンパイラによって生成された XSLT を理解すると、多くの場合に役立ちます。 XSLT の理解によって得ることができるメリットの一部を次に挙げます。  
  
-   ループまたはカスタム Functoid を使用している場合、ループの実行方法やカスタム Functoid の呼び出し方法についての理解が深まります。  
  
-   複雑なマップがある場合は場合、または変換マップを変換する方法を表示することができます、XSLT の確認とが理解する方法の詳細構造を改良し、置換、またはいずれかの合理化にパーツの詳細。  
  
-   カスタム スクリプトまたは他の成果物を使用している場合、XSLT を確認することができます、スクリプト、成果物、およびマップの他の部分がやり取りする方法を参照してください。  
  
 マップの XSLT は簡単な手順で表示できます。  
  
##### <a name="to-view-the-xslt-generated-by-the-map-compiler"></a>マップ コンパイラで生成された XSLT を表示するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをクリックして、**ソリューション エクスプ ローラー** タブで、マップを右クリックし、をクリックして**マップの検証**です。  
  
2.  [出力] ウィンドウをスクロールして、XSL ファイルの URL を探します。 Ctrl キーを押し、URL をクリックすると、ファイルが表示されます。  
  
 手動でマップをカスタマイズする場合は、マップ コンパイラによって生成されたバージョンを変更できます。 変更は、マッパーによって反映されず、次回ソリューションをビルドするときに失われます。  
  
### <a name="tune-your-map-for-specific-scenarios-using-mapsource"></a>特定のシナリオを使用して、マップをチューニング\<mapsource\>  
 属性を変更することによって、マッパーの既定動作の一部を変更することができます、 **mapsource**直接マップ ソース (.btm) ファイル内の要素。 現在、3 つの動作を変更できます。  
  
-   **値のマッピング functoid のコード生成の最適化**です。 変数がいつ `if` ステートメントと共に使用されるかを制御する動作を変更できます。  
  
-   **大きな容量をスキーマに合わせて**です。 内部コンパイラ ノードが大きなマップでどのように使用されるかを変更できます。  
  
-   **ループ、条件、および値のマッピング functoid と使用状況を個々 の管理**です。 `xsl:for-each` ステートメントが送信先スキーマ内のどこで使用されるかを制御できます。  
  
 変更の詳細については**mapsource**を参照してください[を管理する既定のマッパーを使用して動作\<mapsource\>](../core/managing-default-mapper-behavior-using-mapsource.md)です。  
  
## <a name="see-also"></a>参照  
 [[全般] のトラブルシューティングに関する質問と回答](../core/general-troubleshooting-questions-and-answers.md)   
 [一般的なエラー](../core/common-errors.md)