---
title: Siebel アダプターのクライアントの機能 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- features, of the adapter
ms.assetid: 11792629-a692-4378-b522-d33484ee8acb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f929b14415265c4ad9894a16b87294dccd4e906f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222074"
---
# <a name="features-for-siebel-adapter-clients"></a>Siebel アダプターのクライアントの機能
トピックで説明されている機能だけでなく[概要の BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアント用の便利な次の機能します。  
  
-   **バインドのプロパティを使用してアダプターを構成するためのサポート**です。 アダプターのクライアントを構成することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]をメタデータの生成中に特定のバインディング プロパティを指定します。 詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインドのプロパティについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。  
  
-   **操作のパラメーターに null 値のサポート**です。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] XSD"nillable"属性を使用して、ビジネス オブジェクトの操作パラメーターを null 値を提供するアダプターのクライアントを有効にします。 アダプターでは、Siebel システムへの null 値を持つフィールドを渡しません。  
  
-   **XML データのストリーミングをサポートする**です。 アダプターのクライアントがデータからまたはにストリーム配信できます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を使用して、 **XMLReader**または**XMLWriter**インターフェイスです。  
  
-   **BizTalk Server での動的ポートのサポート**です。 BizTalk を通じて[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]からのメッセージの動的なルーティングできるようにする動的なポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。 詳細については、次を参照してください。 [Siebel アダプターと動的ポートを構成する](../../adapters-and-accelerators/adapter-siebel/configure-dynamic-ports-with-the-siebel-adapter.md)です。  
  
-   **メッセージのバージョン管理のサポート**です。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]メッセージ バージョン管理をサポートしています。 これによりサポートされるさまざまなメッセージ スキーマは、の将来のリリース、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[メッセージ バージョン管理サポート](../../adapters-and-accelerators/adapter-siebel/message-versioning-support2.md)です。  
  
-   **パフォーマンス カウンターのサポート**です。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアントが使用できる WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。 [Siebel アダプターのパフォーマンス カウンターを使用して](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)です。  
  
    > [!NOTE]
    >  この機能は、アダプターの以前のバージョンとの下位互換性を提供しません。  
  
-   **XML 要素の名前をエンコードのサポート**です。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]は XML 内の要素名としてのエンタープライズ アプリケーションからのエンティティを表示します。 アンダー スコアは、要素名に含めることができる唯一の特殊な文字です。 したがって、アンダー スコアは、特殊文字を含む要素名のエンコードに使用されます。 たとえば、`emp$name`にエンコードされる`emp_x0024_name`です。  
  
## <a name="see-also"></a>参照  
 [BizTalk adapter 用 Siebel eBusiness Applications の概要](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)