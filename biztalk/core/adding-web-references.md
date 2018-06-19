---
title: Web 参照の追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- orchestrations, BPEL
- Web services, ports
- orchestrations, exporting
- Web services, projects
- Web services, references
- projects, Web services
ms.assetid: 7e40f215-f11a-4151-bcc6-e107bf36b6f6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cbf8cd4c21009190fc459312467656410dc663a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964768"
---
# <a name="adding-web-references"></a>Web 参照の追加
Web ポートを追加するには、BizTalk プロジェクトに Web 参照を追加する必要があります。 Web 参照は、プロジェクトで使用可能な Web サービスの説明です。 プロジェクトに Web 参照を追加すると、BizTalk プロジェクト作成オーケストレーション Web ポートの種類、Web メッセージの種類、Reference.map (マップ ファイル)、Reference.odx (オーケストレーション ファイル)、 \< *WebService*\>です。disco (探索ファイル)、および\< *WebService*\>.wsdl (Web サービス記述言語ファイル) をプロジェクトにします。 Web サービス記述言語 (WSDL) ファイルにスキーマ Web メッセージの種類が含まれる場合、プロジェクトに Reference.xsd が追加されます。  
  
 Web 参照には以下が含まれます。  
  
-   Web サービスの Universal Resource Locator (URL)。  
  
-   使用可能なメソッド、ポート、メッセージの種類などのサービスに関する情報を提供する WSDL ファイル。  
  
-   参照マップ (Reference.map)。  
  
 Web 参照を追加する場合、その Web サービスのすべての Web メソッドには、BizTalk Server との互換性が必要です。 Web サービス内の特定の Web メソッドの条件付き属性を指定することはできません。  
  
 使用して、プロジェクトに Web 参照を追加する、 **Web 参照の追加** ダイアログ ボックス。 Web 参照の追加の詳細については、次を参照してください。 [Visual Studio を使って](../core/using-visual-studio.md)です。  
  
 Business Process Execution Language (BPEL) エクスポート プロセスを使用してオーケストレーションをエクスポートする場合、既存の BizTalk プロジェクトから Web 参照を参照することはできません。 既存の BizTalk プロジェクトから Web 参照を参照すると、BPEL エクスポート プロセスでは、2 つ目の WSDL ファイルが自動生成され、バインド情報が失われます。  
  
## <a name="see-also"></a>参照  
 [Web ポートの作成](../core/creating-web-ports.md)   
 [Web サービスの利用](../core/consuming-web-services.md)