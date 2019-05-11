---
title: Siebel アダプター クライアントの機能 |Microsoft Docs
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
ms.openlocfilehash: 8b168fcab312f53e38556b1e60a81f97538608fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371696"
---
# <a name="features-for-siebel-adapter-clients"></a>Siebel アダプター クライアントの機能
トピックで説明されている機能だけでなく[概要の BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアントに役立つ次の機能を提供します。  
  
- **バインドのプロパティを使用してアダプターを構成するためのサポート**します。 アダプター クライアントを構成することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]メタデータの生成中に特定のバインド プロパティを指定することで。 詳細については、次を参照してください。 [Siebel のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  
  
- **操作のパラメーターに null 値のサポート**します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]によりアダプターでクライアントに XSD"nillable"属性を使用してビジネス オブジェクトの操作パラメーターの null 値を指定します。 アダプターでは、Siebel システムへの null 値を持つフィールドを渡しません。  
  
- **XML データのストリーミングをサポートする**します。 アダプター クライアントからのデータをストリーミングできます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を使用して、 **XMLReader**または**XMLWriter**インターフェイス。  
  
- **BizTalk Server で動的ポートのサポート**します。 BizTalk から[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]からのメッセージの動的ルーティングできるようにする動的ポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。 詳細については、次を参照してください。 [Siebel アダプターの動的ポートを構成する](../../adapters-and-accelerators/adapter-siebel/configure-dynamic-ports-with-the-siebel-adapter.md)します。  
  
- **メッセージのバージョン管理のサポート**します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]メッセージ バージョン管理をサポートしています。 これによりサポートされるさまざまなメッセージ スキーマは、の将来のリリース、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[メッセージ バージョン管理サポート](../../adapters-and-accelerators/adapter-siebel/message-versioning-support2.md)します。  
  
- **パフォーマンス カウンターのサポート**します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアントを使用する WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。 [Siebel アダプターを使用したパフォーマンス カウンターを使用して](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)します。  
  
  > [!NOTE]
  >  この機能は、アダプターの以前のバージョンとの下位互換性を提供しません。  
  
- **XML 要素の名前をエンコードするためのサポート**します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] XML 内の要素名としてのエンタープライズ アプリケーションからエンティティを表示します。 アンダー スコアは、要素名に含めることができる唯一の特殊な文字です。 そのため、アンダー スコアは、特殊文字を含む要素名のエンコードに使用されます。 たとえば、`emp$name`にエンコードが`emp_x0024_name`します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Siebel eBusiness Applications の概要](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)