---
title: "WCF LOB Adapter SDK を使用する場合、URI スキームとアドレス指定の形式の選択 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6df8145fac74761fee4aabd34ff01d708b646c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用する場合に、URI スキームとアドレス指定の形式を選択します。
Uniform Resource Identifier () は、Web サービスのようにまたはの場合、アダプターを使用して開発リソースを一意に識別、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、実行するアクションと同様に、システムに接続します。 このセクションでは、エンドポイント アドレスとアダプターのアクションを記述する URI を作成する方法の推奨事項を提供します。  
  
## <a name="anatomy-of-a-uri"></a>URI の構造  
 URI は、次の 3 つのコンポーネントで構成されます。  
  
-   **スキーム名**潜在顧客、URI 文字列の一部は、最初のレベル名前付け構造体の例としては、http、urn、contoso です。  
  
-   **階層部分**情報は通常階層構造で省略可能な機関、ホスト名、およびポート情報を含めることで構成されます。 例として、www.microsoft.com やユーザー名 =User@microsoft.com:4099です。  
  
-   **クエリ**疑問符 (?) でマークされ、通常、アンパサンドで区切られたキーと値のペアとしてグループ化のオプションの情報が含まれています (&)。 たとえば、contoso://microsoft.com/functions?name=Find です。  
  
-   **フラグメント**アダプターによって必要とされる追加の識別情報を格納するために使用します。 ハッシュで区切られているフラグメント (#)。たとえば、contoso://microsoft.com/functions?name=Find#public です。  
  
 すべての URI の構文によって提供される機能を使用する可能性がありますされません。  
  
## <a name="designing-the-uri"></a>URI の設計  
 アダプター開発者の場合は、ターゲット基幹業務システムの適切な URI を検討する必要があります。 URI を設計する場合は、一意でわかりやすいようにする必要があります。  
  
 一意の URI は、組織内および他の企業間の既存の Uri と、インターネットと競合しないことです。 たとえば、"http"または"afs"現在認識されて既に広く使用でしたを発生したりする接続または運用上の問題と、アダプターが別のシステムには、要求をルーティングすることもあるためと同様にスキーマ名を選択します。  
  
 URI のデザインのもう 1 つの重要な側面はことが意味のある、アダプターを使用している開発者向けです。 たとえばの信頼性情報処理システムを医療のアダプターを作成する場合は、会社名、システム名、およびシステム バージョンを処理対象の信頼性情報を含む URI スキームをデザインでした: northwind.contoso.cps.v1.0:// です。  
  
## <a name="connecting-to-the-target-system"></a>ターゲット システムに接続します。  
 接続文字列では、次の構文があります。  
  
 **\<スキーム >://[userinfo"@"]\<LOB 接続文字列 >**  
  
 たとえば、注文システム (ビジネス アプリケーションのサンプル行)、contoso カタログに接続する可能性があります、次を使用します。  
  
 **northwind.contoso.v1.0://\<servername > ですか?カタログ = Contoso & Integrated Security = True**  
  
 また、ユーザー名とパスワードおよびその他の重要な資格情報を含む URI 内の省略可能な機関情報を提供することができます。 ただし、このセキュリティ上のリスクが発生できます。  
  
> [!CAUTION]
>  ユーザーの資格情報と他の機密情報を URI に渡さないでください。 この情報は、傍受、承認されていないユーザーによって閲覧される可能性があります。  
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)