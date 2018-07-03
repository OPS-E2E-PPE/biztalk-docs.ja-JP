---
title: WCF LOB Adapter SDK を使用する場合は、URI スキームとアドレス指定の形式を選択します |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a9e9ffd78e0740dd366f4f09d3a832e74cda94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005771"
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用する場合は、URI スキームとアドレス指定の形式を選択します
Web サービスのように、使用して開発されたアダプターの場合、リソースを一意に識別する Uniform Resource Identifier (URI)、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を実行するアクションと同様に、システムに接続します。 このセクションでは、エンドポイント アドレスとアダプターのアクションを記述する URI を作成する方法の推奨事項を提供します。  
  
## <a name="anatomy-of-a-uri"></a>URI の構造  
 URI は、次の 3 つのコンポーネントで構成されます。  
  
- **スキーム名**URI 文字列の潜在顧客の一部であり、名前付け構造体の第 1 レベルの例には、http、urn、contoso がなどがあります。  
  
- **階層の一部**情報は通常、階層的で省略可能な機関、ホスト名、およびポート情報を含めることで構成されます。 例としては、www.microsoft.com のユーザー名 =User@microsoft.com:4099します。  
  
- **クエリ**疑問符 (?) でマークされ、通常はアンパサンドで区切られたキーと値のペアとしてグループ化のオプションの情報が含まれています (&)。 たとえば、contoso://microsoft.com/functions?name=Find します。  
  
- **フラグメント**アダプターで必要となる追加の識別情報を格納するために使用します。 ハッシュで区切られた、フラグメント (#)。たとえば、contoso://microsoft.com/functions?name=Find#public します。  
  
  すべての URI 構文によって提供される機能を使用する場合がありますできません。  
  
## <a name="designing-the-uri"></a>URI の設計  
 アダプター開発者は、ターゲットの基幹業務システムの適切な URI を検討する必要があります。 実際の URI を設計するときは、一意でわかりやすいようにする必要があります。  
  
 一意の URI とは、組織内およびその他の企業間の既存の Uri と、インターネットと競合しないです。 たとえば、"http"または現在認識されてしまう可能性や、既に非常に幅広く使用で考えられる原因接続または運用上の問題と、アダプターが別のシステムに要求をルーティングすることもあるため"afs"のようなスキーム名を選択します。  
  
 URI の設計のもう 1 つの重要な側面ことが意味のあるユーザー、アダプターを利用する開発者向け。 たとえばの信頼性情報処理システムを医療、アダプターを作成する場合は、会社名、システム名、およびシステムのバージョンを処理対象のクレームを含む URI スキームをデザインでした: northwind.contoso.cps.v1.0:// します。  
  
## <a name="connecting-to-the-target-system"></a>ターゲット システムに接続します。  
 接続文字列では、次の構文があります。  
  
 **\<スキーム\>://[userinfo"\@"]\<LOB 接続文字列\>**  
  
 たとえば、注文システム (ビジネス アプリケーションのサンプル行)、contoso カタログに接続できます、次を使用します。  
  
 **northwind.contoso.v1.0://\<servername\>でしょうか。カタログ = Contoso & Integrated Security = True**  
  
 ユーザー名とパスワード、およびその他の重要な資格情報を含む URI で省略可能な機関の情報を指定することもできます。 ただし、このセキュリティ リスクを表示できます。  
  
> [!CAUTION]
>  ユーザーの資格情報とその他の機密情報を URI に渡さないでください。 この情報を傍受され、承認されていないユーザーに表示可能性があります。  
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)