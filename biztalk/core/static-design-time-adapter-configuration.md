---
title: 静的デザイン時アダプター構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 332723a4-e39d-43f5-af4d-bf9f56496535
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 081a7ed6fb6892eb08214d1844d98e7d87b503ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392932"
---
# <a name="static-design-time-adapter-configuration"></a>静的デザイン時アダプター構成
アダプターのデザイン時部分では、使用可能なすべてのプロパティを定義し、ユーザー入力を検証します。 アダプターの静的デザイン時構成では、既定のユーザー インターフェイス (UI) を使用して、そのプロパティを表示および編集します。  
  
 このセクションでは、カスタム アダプターの静的デザイン時構成機能を実装する方法について説明します。 どのように変更するかは、アダプターが通信するアプリケーションの要件、およびアダプターが実装するロジックに基づいて決定します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプでこれらの手順や背景情報が詳しく説明されている場合は、該当するセクションへのリンクが表示されます。 また、サンプル ファイルのアダプター ドキュメント内で、関連する例が記載されている部分を参照することもできます。  
  
## <a name="guidelines-for-the-static-development-process"></a>静的な開発プロセスのガイドライン  
 以下に、静的デザイン時機能をアダプターに組み込む場合の推奨事項を示します。 開発中は、これらの手順をすべて実行する必要はありません。また、記述されているとおりの順序で実行する必要もありません。  
  
1. アダプター構成要件、および設定する必要がある構成パラメーターの一覧を作成します。 すべての受信場所と送信ポートでグローバルに使用するパラメーターは、ハンドラー スキーマ構成ファイルで指定します。 特定のポートまたは特定の場所で使用するパラメーターは、送信ポート構成ファイルと受信場所構成ファイルでそれぞれ構成します。  
  
2. アダプターのプロパティ ページを新しい構成パラメーターに対応するように変更します。 この手順の詳細については、次を参照してください。[アダプター構成スキーマ](../core/adapter-configuration-schemas.md)します。  
  
3. アダプター メタデータの追加ウィザードを使用して、スキーマ カテゴリのツリー ビューを変更します。 この手順の詳細については、次を参照してください[アダプター メタデータの追加ウィザードのスキーマ カテゴリ。](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)  
  
4. スキーマが Web サービス記述言語 (WSDL) ファイルとして返されるようにサンプル コードを修正します。 この手順の詳細については、次を参照してください。[静的アダプターの IStaticAdapterConfig インターフェイス](../core/static-adapter-istaticadapterconfig-interface.md)します。  
  
5. 既存の WSDL ファイルを変更するか、新しい WSDL ファイルを作成します。 この手順の詳細については、次を参照してください。[アダプター WSDL ファイル](../core/adapter-wsdl-files.md)します。  
  
6. サンプル コードを変更して、WSDL ファイルに含まれていないアダプターによって必要とされている追加の XSD ファイルを返します。 この手順の詳細については、次を参照してください。[アダプターの GetSchema メソッド](../core/adapter-getschema-method.md)します。  
  
7. アダプターのレジストリ キーを変更して、アダプターのレジストリ ファイルを実行します。 この手順の詳細については、次を参照してください。[アダプターの登録ファイル](../core/adapter-registration-file.md)します。  
  
8. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に静的アダプターをインストールします。 この手順の詳細については、次を参照してください。[アダプターを BizTalk Server インストール](../core/install-the-adapter-into-biztalk-server.md)します。  
  
9. アダプターのプロパティ ページに対して行われた変更をテストします。 アダプターを再ビルドして、アダプター メタデータの追加ウィザードに表示される UI をテストします。 この手順の詳細については、次を参照してください[のビルドとアダプター プロジェクトのテスト。](../core/build-and-test-the-adapter-project.md)  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [静的アダプターの IStaticAdapterConfig インターフェイス](../core/static-adapter-istaticadapterconfig-interface.md)  
  
-   [アダプター メタデータの追加ウィザードのスキーマ カテゴリ](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)