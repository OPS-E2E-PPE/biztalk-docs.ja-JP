---
title: WCF アダプターに関する FAQ:WCF エンドポイント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccc94b7d-b8a6-4c24-907e-922fd885b874
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56e1e7b657b0c365675e3b7f308d7960c12968f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393567"
---
# <a name="wcf-adapter-faq-wcf-endpoints"></a>WCF アダプターに関する FAQ:WCF エンドポイント
## <a name="what-are-two-endpoints-options-can-be-created-by-the-biztalk-wcf-service-publishing-wizard"></a>2 つのエンドポイント オプションは、BizTalk WCF サービス公開ウィザードによって作成できますか。  
 BizTalk WCF サービス公開ウィザードを実行するときに、WCF サービスのエンドポイントまたは WCF メタデータ専用エンドポイント (MEX) を作成する選択できます。  
  
 サービス エンドポイントは、実際の WCF サービスの機能を公開する IIS でホストされている実際の Web の場所を作成します。 分離アダプターのみ (Wcf-wshttp、Wcf-basichttp、および Wcf-customisolated) は、サービス エンドポイントで使用できます。 この種類のエンドポイントの機能は、オーケストレーションまたは WCF サービスとして公開されるスキーマによって実装されます。  
  
 メタデータ専用エンドポイントが機能を持つが、BizTalk によって実装が 1 つの受信場所。  これを使用して IIS と、インプロセス WCF によって公開されているオーケストレーションや実際の WCF サービス コードではなく、受信アダプター。 簡単な方法で統合情報を提供する公開メタデータ専用エンドポイントを生成するウィザードを使用して svcutil.exe を使用して手動で実行するより、インプロセス WCF アダプターを使用して場所を受信します。 Svcutil.exe を使用して強制的に呼び出すことができるため、サービスのコンシューマーにメタデータを転送する方法を見つけることにします。  
  
## <a name="why-would-i-use-a-metadata-only-endpoint-in-biztalk-server"></a>メタデータ専用エンドポイントを BizTalk Server の使用は  
 メタデータのみのエンドポイントを持つ、サービスの実装が実際の WCF サービスにありません。 BizTalk の機能を実装する代わりに、受信場所、サービス エンドポイントと WCF サービスと同様に呼び出されます。 たとえば、2 つのスキーマとメッセージのフィールドを受け取り、すべて大文字に変換するマップがある可能性があります。 この場合、サービスは、"ConvertToUpper"としてメタデータでパブリッシュされます。 サービスの機能は、受信場所で、コードではなく、またはオーケストレーションで実装されます。  
  
 WCF エンドポイントは、アドレス、バインディング、およびコントラクトで構成されます。 ウィザードでは、メタデータ専用エンドポイントを作成したときに、アドレスを取得し、受信場所が既に既存のファイルからのバインディングの詳細。 コントラクト情報が、BizTalk オーケストレーション内にあるスキーマによって定義されている、またはウィザードを使用して手動で作成することができます。 選択した場合**BizTalk オーケストレーションを WCF サービスとして発行**、メタデータ専用エンドポイントでは、オーケストレーション アセンブリからのメッセージとポートの種類を使用して、コントラクトを定義します。  
  
 選択した場合**スキーマを WCF サービスとして公開**ウィザードでは、既存の入力と出力スキーマを備えたサービスと操作の名前を指定することで、サービスの定義を定義することができます。 ウィザードでは、パブリッシュした後、メタデータを参照できるように、.svc ファイルと IIS 仮想ディレクトリを作成します。 BizTalk WCF サービス公開ウィザードの httpGetEnabled 属性と web.config ファイルが作成されます、 \<serviceMetadata\>要素が true に設定します。 これを参照するためのメタデータを公開します。 使用して HTTP 経由で GET 要求でそのデータをアクセスできますを BizTalk の受信場所のサービス メタデータを公開する場合、`?wsdl`サービスの URL の末尾にします。  
  
## <a name="are-service-endpoints-hosted-in-iis-and-why"></a>IIS でホストされるサービス エンドポイントとその理由ですか?  
 はい、サービス エンドポイントは、次の 3 つの分離アダプターのいずれかを使用して IIS でホストされます。  
  
- Wcf-wshttp  
  
- WCF-BasicHttp  
  
- WCF-CustomIsolated  
  
  サービス エンドポイントは、その機能は、WCF サービスとして直接呼び出すことができますでメタデータ専用エンドポイントとは異なります。 指定した BizTalk アプリケーションでの受信場所の BizTalk WCF サービス公開ウィザードを使用して、新しいサービス エンドポイントの結果を作成します。 オーケストレーションを IIS を通じてアクセスできる URI を定義します。  
  
## <a name="when-creating-a-service-endpoint-why-would-i-select-to-publish-schemas-as-a-wcf-service"></a>サービス エンドポイントを作成する場合は「スキーマを WCF サービスとして公開する」には選択ですか。  
 選択すると、BizTalk メッセージングのみを使用している BizTalk アプリケーションの一部では、WCF 受信場所の場合は、WCF サービスは、スキーマを公開します。 これは、使用されているオーケストレーションがないと、すべての機能が、受信場所を通じて公開され、送信ポートを意味します。 スキーマをパブリッシュすると、コントラクト情報を指定します。 この情報または取得できます、スキーマ アセンブリから、オーケストレーション アセンブリからでも (ただし、オーケストレーションをこのエンドポイントに使用することはできません)。