---
title: ソース スキーマと送信先スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- destination schemas
- source schemas, maps
- XML schemas, defining
- destination schemas, about destination schemas
- schemas, destination
- destination schemas, maps
- maps, source schemas
- schemas, Root Reference property
- Root Reference property, modifying
- source schemas
- modifying, Root Reference property
- maps, Root Reference property
- source schemas, about source schemas
- schemas, maps
- maps, schema requirements
- schemas, requirements
- schemas, source schemas
- maps, destination schemas
- Root Reference property
ms.assetid: 8c805854-9fa1-4ce3-938d-a2e61ba17fa1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f873c9dcd38c476ea47ea57e412aeec51e239b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243273"
---
# <a name="source-and-destination-schemas"></a>送信元スキーマと送信先スキーマ
各 BizTalk マップには、2 つのスキーマが使用されます。 送信元スキーマと送信先スキーマです。 送信元スキーマは、データの取得元となるインスタンス メッセージの構造を定義します。 送信先スキーマは、マップによって生成されるインスタンス メッセージの構造を定義します。 たとえば、注文書から請求書に出荷先情報および請求先情報をマップする場合、送信元スキーマに注文書を定義するスキーマ、送信先スキーマに請求書を定義するスキーマが必要です。  
  
 BizTalk マップで使用されるスキーマでは、次の条件を満たす必要があります。  
  
- 現在の BizTalk プロジェクトの一部に送信元スキーマおよび送信先スキーマを組み込む必要があります。また、実行中にスキーマへアクセスするために、アセンブリにスキーマへの参照を組み込む必要があります。  
  
- BizTalk マッパーで使用されるスキーマは、XSD (XML Schema Definition) 言語に基づいている必要があります。 BizTalk エディターを使用すると、このようなスキーマを簡単に作成できます。 BizTalk エディターでスキーマの作成の詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)します。 参照してください[スキーマの作成](../core/creating-schemas.md)です。  
  
  BizTalk エディターでは、複数のルート ノードがあるスキーマを作成できます。 ただし、BizTalk マップで複数のルート ノードがあるスキーマを使用する場合は、マップで使用するルート ノード (および対応するサブ構造体) を選択する必要があります。 スキーマが、**ルート参照**ルートを識別するプロパティが主キー。 スキーマに複数のルートと**ルート参照**スキーマ最初として開く場合は、ソースまたは変換先スキーマの BizTalk マッパーは、指定したルート プロパティが設定されます。 スキーマに複数のルートと**ルート参照**プロパティが設定されていない、BizTalk マッパーでは、ルートを選択するように求められます。  
  
  変更した場合、**ルート参照**既に、マップを BizTalk マッパーで使用されるスキーマのプロパティが変更気付くことはありません、最初に指定されたルートを使用し続けるとします。 同じスキーマの異なるルートを使用して別のマップを構築する場合に設定しないお勧め、**ルート参照**プロパティ。 この場合、新しいマップでスキーマを使用するたびに、明示的にルートを選択する必要があります。  
  
  マップにスキーマを含めた後にスキーマを編集すると、マップ内のリンクが壊れる可能性があります。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)