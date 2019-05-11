---
title: プロジェクト項目の追加 |Microsoft Docs
description: オーケストレーション、スキーマ、マップ、およびパイプラインを Visual Studio で BizTalk Server プロジェクトに追加します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1b922d5-8ece-4e1a-a390-e6ae1222665a
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b0fc88bcf2f843e7d22b47a69ccae1b7b3fcd66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360918"
---
# <a name="add-project-items"></a>プロジェクト項目を追加します。
BizTalk プロジェクト システムのコンテキストでは、プロジェクト項目は、マップやスキーマなど、構成されている項目です。 BizTalk アプリケーションには、1 つまたは複数のオーケストレーション、スキーマ、マップ、およびパイプラインが含まれます。  
  
> [!NOTE]
>  プロジェクトに項目を追加するときに、ピリオドは .NET 名前空間を区切るのため名にピリオド (.) を使用しないでください。 項目名にピリオドを使用する場合、項目の型名にはピリオドの代わりにアンダー スコア (_) が含まれます。  
  
> [!NOTE]
>  フォルダーにスキーマ、マップ、またはパイプラインを追加すると、**完全修飾名**プロパティが自動的に生成し、名前空間と型が含まれています。  
  
## <a name="orchestrations"></a>オーケストレーション  
 オーケストレーションは、xlang/s 言語で表されるビジネス プロセスの表現です。 XLANG/秒は、Microsoft などの既存の手続き型言語を補完するために使用できます[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]と Microsoft[!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)]します。  
  
 オーケストレーション デザイナーを使用して、BizTalk プロジェクトに追加するオーケストレーションを作成することができます。 オーケストレーション デザイナーで作成したすべてのオーケストレーションには、.odx ファイル拡張子があります。  
  
## <a name="schemas"></a>スキーマ  
 スキーマは、ドキュメントまたはメッセージの構造体の定義です。 レコードおよびフィールド構造内の関連プロパティ情報が含まれます。 該当する場合は、スキーマは、複数のサブスキーマを含めることができます。  
  
 BizTalk エディターを使用して、インポート、編集、またはスキーマを作成することができます。 BizTalk マッパーでマップを生成するために作成するスキーマを使用できます。 すべてのスキーマを BizTalk エディターを使用して保存するには、.xsd ファイル拡張子があります。  
  
 スキーマと BizTalk エディターの詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)します。  
  
## <a name="maps"></a>マップ  
 マップとは別のスキーマのレコードとフィールドを 1 つのスキーマのレコードとフィールドの間の対応を定義する XML ファイル。 業界標準、非業界標準 (内部標準や従来問題など)、または既存のファイルに基づくマップを作成します。 受信または別の 1 つの形式から送信されるデータを変換する場合に、マップを作成します。 BizTalk マッパーを使用すると、BizTalk プロジェクトに含めるマップを作成します。 BizTalk マッパーで保存するすべてのマップには、.btm ファイル拡張子が付いています。 BizTalk マッパーの詳細については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)します。  
  
## <a name="pipelines"></a>パイプライン  
 パイプライン デザイナーを使用して、作成する受信パイプラインと送信されます。 パイプラインは、定義および BizTalk Server によって送信または受信したメッセージを処理するための 1 つまたは複数のステージをリンクするソフトウェア インフラストラクチャです。 パイプラインは、特定の順序で、ステージを実装し、エンコードまたはデコード、アセンブルや逆アセンブル、および暗号化または暗号化解除などの関数が含まれます。  
  
 BizTalk プロジェクトに含まれる既定のパイプライン参照は、XML ドキュメントのみを処理できます。 フラット ファイル、EDI ドキュメント、またはその他のファイルの種類を処理する場合は、に応じて新しいパイプラインを作成する必要があります。 パイプライン デザイナーで作成されたすべてのパイプラインには、.btp 拡張子が付いています。 パイプラインおよびパイプライン デザイナーの詳細については、次を参照してください。[パイプライン デザイナーを使用してパイプラインを作成](../core/creating-pipelines-using-pipeline-designer.md)です。  
  
## <a name="valid-files-for-biztalk-projects"></a>BizTalk プロジェクトの有効なファイル  
 BizTalk プロジェクトを使用する場合は、HTML ファイル、XML ファイルの場合は、受信パイプライン ファイル、およびスキーマ ファイルなど、多数の異なるファイルを含めることができます。 BizTalk Server では、Visual Studio のビルド システムでサポートされている任意のオブジェクトが、アセンブリに含めることができます。  
  
## <a name="see-also"></a>参照  
 [BizTalk プロジェクトの操作](../core/working-with-biztalk-projects.md)