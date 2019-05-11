---
title: マップのトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: d6d87a5577ba8472b9d82df27f340b3361bc6b89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295718"
---
# <a name="troubleshooting-maps"></a>マップのトラブルシューティング
このトピックではトラブルシューティングの方法、問題の詳細の解決情報がマップされます。  
  
## <a name="troubleshooting-strategies"></a>トラブルシューティングの方法  
  
### <a name="validate-your-map"></a>マップを検証します。  
 当然のことが常に、開発中のさまざまな時点で、マップを検証する必要があります。 これがそれらを修正するか、別のソリューションを検索しやすく、開発サイクルの早い段階でのデザイン、ロジック、およびスキーマの問題の識別に役立ちます。  
  
##### <a name="to-validate-a-biztalk-map"></a>BizTalk マップを検証するには  
  
1.  ソリューション エクスプ ローラーで、検証するマップを開きます。  
  
2.  ソリューション エクスプ ローラーで、マップを右クリックし をクリックし、**マップの検証**です。  
  
3.  [出力] ウィンドウで、結果を確認します。  
  
> [!NOTE]
>  マップを検証するときに、参照、スキーマで定義されている任意のデータ型に違反しているかどうかに、テスト インスタンス データはチェックされません。 マップのテストまたは BizTalk エディターでインスタンス データを検証するときに、インスタンス データを確認できます。  
  
### <a name="review-the-xslt-generated-for-your-map"></a>マップの生成された XSLT を確認してください。  
 マップ コンパイラによって生成された XSLT を理解すると便利です。 XSLT を検査する利点のいくつか挙げます。  
  
- ループまたはカスタム functoid を使用している場合は、ループの実行方法とカスタム functoid を呼び出す方法をより深く理解されます。  
  
- 複雑なマップがある場合は、XSLT の確認を変換に、マップを変換する方法を確認することは有効にしてある方法についての見識構造を改良し、置換、またはいずれかの効率化するまたはパーツの詳細はします。  
  
- カスタム スクリプトや他の成果物を使用している場合、XSLT の確認ができます、スクリプト、成果物、およびマップの他の部分がやり取りする方法を参照してください。  
  
  さいわい、マップの XSLT を表示する、簡単なプロセスです。  
  
##### <a name="to-view-the-xslt-generated-by-the-map-compiler"></a>マップ コンパイラによって生成された XSLT を表示するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをクリックして、**ソリューション エクスプ ローラー** タブで、マップを右クリックし、をクリックして**マップの検証**です。  
  
2. XSL ファイルの URL を確認する出力ウィンドウをスクロールします。 Ctrl キーを押し、URL をクリックすると、ファイルが表示されます。  
  
   手動でマップをカスタマイズする場合は、マップ コンパイラによって生成されたバージョンを変更できます。 変更は、マッパーによって反映されず、され、次にソリューションをビルドするときが失われます。  
  
### <a name="tune-your-map-for-specific-scenarios-using-mapsource"></a>使用して特定のシナリオに対して、マップを調整\<mapsource\>  
 属性を変更することで、マッパーの既定動作の一部を変更することができます、 **mapsource**直接マップ ソース (.btm) ファイル内の要素。 現在、変更可能な 3 つの動作があります。  
  
- **値のマッピング functoid のコード生成の最適化**します。 変数を使用するときを制御する動作を変更する`if`ステートメント。  
  
- **大きな容量を使用するスキーマの調整**します。 内部コンパイラ ノードは、大規模なマップでの使用方法を変更することができます。  
  
- **ループ、条件、および値のマッピング functoid と for-each の使用を管理**します。 場所を制御することができます、`xsl:for-each`送信先スキーマ内でステートメントを使用します。  
  
  変更の詳細については**mapsource**を参照してください[を管理する既定のマッパーを使用して動作\<mapsource\>](../core/managing-default-mapper-behavior-using-mapsource.md)します。  
  
## <a name="see-also"></a>参照  
 [一般的なトラブルシューティングに関する質問と回答](../core/general-troubleshooting-questions-and-answers.md)   
 [一般的なエラー](../core/common-errors.md)