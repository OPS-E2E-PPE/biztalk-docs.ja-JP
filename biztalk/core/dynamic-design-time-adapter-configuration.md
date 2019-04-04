---
title: 動的デザイン時アダプター構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36127d62-0348-42bb-981f-19fcad26efce
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e54d45c920fa430880e7a51d66ae500bfa9e13af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988147"
---
# <a name="dynamic-design-time-adapter-configuration"></a>動的デザイン時アダプター構成
静的デザイン時アダプター構成とアダプター メタデータの追加ウィザードの標準の既定 UI では、インポートする BizTalk プロジェクトのアダプターのサービスを表示するための柔軟性が足りない場合があります。 代わりに、動的デザイン時構成を使用できます。この構成では、カスタマイズした UI をウィザードに提供し、アダプターのサービスを表示および選択できます。 BizTalk アダプター フレームワークには、アダプターに必要なスキーマのインポートやカスタム UI の表示に使用できる一連の API が用意されています。  
  
 このセクションでは、カスタム アダプターの動的デザイン時構成機能を実装する方法について説明します。 どのように変更するかは、アダプターが通信するアプリケーションの要件、およびアダプターが実装するロジックに基づいて決定します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプでこれらの手順や背景情報が詳しく説明されている場合は、該当するセクションへのリンクが表示されます。 また、サンプル ファイルのアダプター ドキュメント内で、関連する例が記載されている部分を参照することもできます。  
  
## <a name="guidelines-for-the-dynamic-development-process"></a>動的な開発プロセスのガイドライン  
 以下に、動的デザイン時機能をアダプターに組み込む場合の推奨事項を示します。 開発中にするは、これらすべての手順を行うも厳密なシーケンスで実行する必要はありません。  
  
1. アダプター構成要件、および設定する必要がある構成パラメーターの一覧を作成します。 すべての受信場所と送信ポートでグローバルに使用するパラメーターは、ハンドラー スキーマ構成ファイルで指定します。 特定のポートまたは特定の場所で使用するパラメーターは、送信ポート構成ファイルと受信場所構成ファイルでそれぞれ構成します。  
  
2. アダプターのプロパティ ページを新しい構成パラメーターに対応するように変更します。 この手順の詳細については、[アダプター構成スキーマ](../core/adapter-configuration-schemas.md)を参照してください。  
  
3. アダプター メタデータの追加ウィザード用のカスタム ユーザー インターフェイス (UI) を作成し、スキーマを選択してプロジェクトに追加します。 ここに記載されているすべての推奨事項の中で、動的アダプターが静的アダプターと異なるのはこの点だけです。 この手順の詳細については、[動的アダプターの DisplayUI メソッド](../core/dynamic-adapter-displayui-method.md)とクラス[Microsoft.BizTalk.Adapter.Framework.IDynamicAdapterConfig.DisplayUI](http://msdn.microsoft.com/library/microsoft.biztalk.adapter.framework.idynamicadapterconfig.displayui.aspx)を参照してください。  
  
4. スキーマが Web サービス記述言語 (WSDL) ファイルとして返されるようにサンプル コードを修正します。 この手順の詳細については、[静的アダプターの IStaticAdapterConfig インターフェイス](../core/static-adapter-istaticadapterconfig-interface.md)を参照してください。  
  
5. 既存の WSDL ファイルを変更するか、新しい WSDL ファイルを作成します。 この手順の詳細については、[アダプター WSDL ファイル](../core/adapter-wsdl-files.md)を参照してください。  
  
6. サンプル コードを変更して、WSDL ファイルに含まれていないアダプターによって必要とされている追加の XSD ファイルを返します。 この手順の詳細については、[アダプターの GetSchema メソッド](../core/adapter-getschema-method.md)を参照してください。  
  
7. アダプターのレジストリ キーを変更して、アダプターのレジストリ ファイルを実行します。 この手順の詳細については、[アダプターの登録ファイル](../core/adapter-registration-file.md)を参照してください。  
  
8. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に静的アダプターをインストールします。 この手順の詳細については、[アダプターを BizTalk Server インストール](../core/install-the-adapter-into-biztalk-server.md)を参照してください。  
  
9. アダプターのプロパティ ページに対して行われた変更をテストします。 アダプターを再ビルドして、アダプター メタデータの追加ウィザードに表示される UI をテストします。 この手順の詳細については、次を参照してください[のビルドとアダプター プロジェクトのテスト。](../core/build-and-test-the-adapter-project.md)  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [動的アダプターの DisplayUI メソッド](../core/dynamic-adapter-displayui-method.md)