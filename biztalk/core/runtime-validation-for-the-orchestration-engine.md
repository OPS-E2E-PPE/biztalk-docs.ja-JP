---
title: オーケストレーション エンジンの実行時の検証 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, assemblies
- orchestrations, validating
- validating, orchestration engine
- schemas, validating
- correlations, validating
- validating, schemas
- orchestration engine, runtime validation
- assemblies, validating
- validating, correlations
- validating, orchestrations
- validating
ms.assetid: f6085889-05d6-4eba-a528-9d034c4e4225
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e53adb5aa42c7dfe23df50707754bde200ea838a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269266"
---
# <a name="runtime-validation-for-the-orchestration-engine"></a>オーケストレーション エンジンの実行時の検証
オーケストレーション エンジンを構成して、オーケストレーションのテスト、および構成やデータの潜在的なエラーの診断をサポートする、さまざまな実行時検証を実行できます。  
  
 これを行うには、BTSNTSvc.exe (通常は BizTalk の展開ディレクトリに格納される) と同じディレクトリにある BTSNTSvc.exe.config という構成ファイルで、フラグを設定します。 BTSNTSvc.exe.config ファイルには次のフラグを設定できます。  
  
-   設定した場合、 **ValidateAssemblies**フラグを`True`エンジンが、エラーをスロー時と、オーケストレーションの即時の依存アセンブリによって参照されるすべてのアセンブリを読み込みしようとしています。Microsoft.XLANGs.Core.AssemblyValidationException です。  
  
-   設定した場合、 **ValidateSchemas**フラグを`True`エンジンは System.Xml.XmlValidatingReader を使用してメッセージ部分の型を表すすべてのスキーマを検証して、エラー発生時に System.Xml.XmlException をスローします。  
  
-   設定した場合、 **ValidateCorrelations**フラグを`True`エンジンは、受信、コンボイのいずれかと一致する関連付けプロパティの値が同じであるし、エラー発生時にスローのすべてのメッセージをコンボイで、並列にことを確認Microsoft.XLANGs.Core.CorrelationValidationException です。  
  
-   設定した場合、 **ExtendedLogging**フラグを`True`エンジンは、公開に失敗したメッセージをスローする Microsoft.XLANGs.BaseTypes.PublishMessageException の情報を昇格させたプロパティを表示します。  
  
 フラグを構成ファイルから完全に削除すれば、検証を無効にできます。 すべての検証が有効化されている場合は、アセンブリ、スキーマ、および関連付けの検証がオーケストレーション エンジンによって実行されます。 詳細と BTSNTSvc.exe.config の例については、次を参照してください。[オーケストレーション エンジンの構成](../core/orchestration-engine-configuration.md)です。  
  
## <a name="validate-assemblies"></a>アセンブリを検証します。  
 オーケストレーション エンジンでは、オーケストレーションによって参照され、かつアクセスの可能なすべてのアセンブリが検証されます。 検証に合格するためには、オーケストレーションの最初のインスタンスがアクティブ化されるときに、すべての参照アセンブリがグローバル アセンブリ キャッシュ (GAC) に存在する必要があります。 検証に失敗すると、アプリケーション ログにエラーが記録され、オーケストレーションが中断されます。  
  
## <a name="validate-schemas"></a>スキーマの検証  
 オーケストレーション エンジンでは、XSD 要素が割り当てられている場合、その要素のデータがスキーマと照合され、検証されます。 検証に失敗すると、アプリケーション ログにエラーが記録され、例外がスローされます。  
  
## <a name="validate-correlation"></a>関連付けの検証  
 オーケストレーション エンジンでは、特定のオーケストレーション インスタンスとの関連付けに指定されたプロパティの値が、そのオーケストレーション インスタンスから送信されるすべてのメッセージに反映されているかを検証します。 場合**validateCorrelation**が設定された場合、エンジンとします。 送信したメッセージには、正しい関連付けの値が含まれています。 チェックは実行されません。  
  
 関連付けの検証に失敗した場合、エンジンは、アプリケーション ログにエラーを記録し、型の例外をスロー **CorrelationValidationException**です。  
  
 既定では、 **validateCorrelation**が設定されていません。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションのデバッグ](../core/debugging-orchestrations.md)   
 [オーケストレーション エンジンの構成](../core/orchestration-engine-configuration.md)