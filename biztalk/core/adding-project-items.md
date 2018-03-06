---
title: "プロジェクト項目の追加 |Microsoft ドキュメント"
description: "オーケストレーション、スキーマ、マップ、およびパイプラインを Visual Studio で BizTalk Server プロジェクトに追加します。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1b922d5-8ece-4e1a-a390-e6ae1222665a
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef998865a1851e546a3648b60e0141b3cd137c1b
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="add-project-items"></a>プロジェクト項目を追加します。
BizTalk プロジェクト システムのコンテキストでは、プロジェクト項目は構成済みの項目のことであり、マップやスキーマなどがあります。 BizTalk アプリケーションには、1 つ以上のオーケストレーション、スキーマ、マップ、およびパイプラインを含めることができます。  
  
> [!NOTE]
>  項目をプロジェクトに追加する場合は、名前にピリオド (.) を使用しないでください。ピリオドは .NET 名前空間の区切り記号であるためです。 項目名にピリオドを使用すると、項目の型名にピリオドの代わりにアンダースコア (_) が含まれます。  
  
> [!NOTE]
>  スキーマ、マップ、またはパイプラインをフォルダーに追加すると、 **完全修飾名** プロパティが自動的に生成し、名前空間と型が含まれています。  
  
## <a name="orchestrations"></a>オーケストレーション  
 オーケストレーションとは、XLANG/s 言語で表現されたビジネス プロセスを表すものです。 XLANG/s は、既存の手続き型言語 (Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] や Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)] など) を補完するために使用できます。  
  
 オーケストレーション デザイナーを使用すると、BizTalk に含めるオーケストレーションを作成できます。 オーケストレーション デザイナーで作成したすべてのオーケストレーションには、.odx ファイル拡張子が付きます。  
  
## <a name="schemas"></a>スキーマ  
 スキーマとは、ドキュメントまたはメッセージの構造の定義です。 構造内のレコードおよびフィールドに関連するプロパティ情報が含まれます。 必要に応じて、スキーマには複数のサブスキーマを含めることができます。  
  
 BizTalk エディターを使用して、スキーマをインポート、編集、または作成できます。 作成したスキーマを使用して、BizTalk マッパーでマップを生成できます。 BizTalk エディターで保存したすべてのスキーマには、.xsd ファイル拡張子が付きます。  
  
 スキーマと BizTalk エディターの詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)です。  
  
## <a name="maps"></a>マップ  
 マップとは、あるスキーマと別のスキーマのレコードおよびフィールドの対応関係を定義した XML ファイルです。 業界標準、非業界標準 (内部標準や従来の問題など)、または既存のファイルに基づいてマップを作成します。 受信または送信するデータを 1 つの形式から別の形式に変換する場合に、マップを作成します。 BizTalk マッパーを使用して、BizTalk プロジェクトに含めるマップを生成できます。 BizTalk マッパーで保存したすべてのマップには、.btm ファイル拡張子が付きます。 BizTalk マッパーの詳細については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)です。  
  
## <a name="pipelines"></a>パイプライン  
 パイプライン デザイナーを使用して、受信および送信パイプラインを作成できます。 パイプラインを定義および BizTalk Server によって送信または受信したメッセージを処理するための 1 つまたは複数のステージをリンクするソフトウェア インフラストラクチャです。 パイプラインには、複数のステージが特定の順序で実装され、エンコードやデコード、アセンブルや逆アセンブル、暗号化や復号化などの機能が取り込まれます。  
  
 BizTalk プロジェクトに含まれる既定のパイプライン参照は、XML ドキュメントのみを処理できます。 フラット ファイル、EDI ドキュメント、またはその他の種類のファイルを処理する場合、必要に応じて新しいパイプラインを作成してください。 パイプライン デザイナーで作成されたすべてのパイプラインには、.btp 拡張子が付きます。 パイプラインおよびパイプライン デザイナーの詳細については、次を参照してください。[パイプライン デザイナーを使用してパイプラインを作成する](../core/creating-pipelines-using-pipeline-designer.md)です。  
  
## <a name="valid-files-for-biztalk-projects"></a>BizTalk プロジェクトの有効なファイル  
 BizTalk プロジェクトで作業する場合、HTML ファイル、XML ファイル、受信パイプライン ファイル、スキーマ ファイルなど、多数の異なるファイルを含めることができます。 BizTalk Server アセンブリは、Visual Studio のビルド システムでサポートされている任意のオブジェクトを含めることができます。  
  
## <a name="see-also"></a>参照  
 [BizTalk プロジェクトでの作業](../core/working-with-biztalk-projects.md)