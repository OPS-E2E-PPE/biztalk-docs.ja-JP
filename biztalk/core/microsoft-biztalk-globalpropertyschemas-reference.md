---
title: Microsoft.BizTalk.GlobalPropertySchemas 参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2acf3083-a0a9-483f-88bf-8023d9933e1e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8e24cee64b5f03b212fabd7003f8ba3586b1c22
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982883"
---
# <a name="microsoftbiztalkglobalpropertyschemas-reference"></a>Microsoft.BizTalk.GlobalPropertySchemas 参照
**Microsoft.BizTalk.GlobalPropertySchemas**名前空間には、さまざまな BizTalk Server コンポーネントを使用するプロパティのプロパティ スキーマが含まれています。 この名前空間に含まれているプロパティは、BizTalk エンジンが使用するシステム プロパティ、各トランスポートが構成を処理するために使用するトランスポート固有のプロパティ、およびパイプライン コンポーネントを構成するプロパティです。  

## <a name="namespace-schemas"></a>Namespace スキーマ  

 次の表に、グローバル プロパティ スキーマに含まれる、 **Microsoft.BizTalk.GlobalPropertySchemas**名前空間。  


|                                                                                                                                                              プロパティ スキーマ                                                                                                                                                              |                                                                                                                                                               機能の領域および説明                                                                                                                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                          bts-btf2-properties.xsd                                                                                                                                                          |                                                                                                                                                                     プロパティ スキーマ :                                                                                                                                                                       |
|                                             btf2-endpoints-header.xsd<br /><br /> btf2-envelope.xsd<br /><br /> btf2-manifest-header.xsd<br /><br /> btf2-process-header.xsd<br /><br /> btf2-properties-header.xsd<br /><br /> btf2-receipt-header.xsd<br /><br /> btf2-services-header.xsd                                              |                                                                                                   BizTalk Framework コンストラクターを定義するスキーマ。 これらのスキーマは、BizTalk Framework アセンブラー パイプライン コンポーネントおよび BizTalk Framework 逆アセンブラー パイプライン コンポーネントに固有のスキーマです。                                                                                                   |
|                                                                                                                                                         bts-system-properties.xsd                                                                                                                                                         | これは、システム プロパティ スキーマです。 BizTalk エンジンは、このスキーマのほとんどのプロパティを使用します。 メッセージのルーティングに一部のプロパティを使用できます。 メッセージのルーティングに使用できるプロパティの詳細については、**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。 |
|                                                                                                                                                        bts-endpoint-properties.xsd                                                                                                                                                        |                                                                                                                                                           これは、内部プロパティ スキーマです。                                                                                                                                                            |
|                                                                                                                                      bts-mime-properties.xsd<br /><br /> bts-xmlnorm-properties.xsd                                                                                                                                       |                                                                                                      パイプライン コンポーネントのプロパティ スキーマです。 MIME、XML、フラット ファイル、および BizTalk Framework アセンブラーおよび逆アセンブラー パイプライン コンポーネント。                                                                                                      |
|                                                                                                                                                    bts-messagetracking-properties.xsd                                                                                                                                                     |                                                                                                                                                           追跡エンジンは、このスキーマを使用します。                                                                                                                                                           |
| bts-file-properties.xsd<br /><br /> bts-ftp-properties.xsd<br /><br /> bts-http-properties.xsd<br /><br /> bts-pop3-properties.xsd<br /><br /> bts-smtp-properties.xsd<br /><br /> soap-encoding_1__1.xsd<br /><br /> soap-envelope_1__1.xsd<br /><br /> bts-soap-properties.xsd<br /><br /> bts-WindowsSharePointServices-properties.xsd |                                                               トランスポート固有のプロパティ スキーマです。 トランスポートは、これらのスキーマを使用して、特定のトランスポート情報および構成を転送します。 トランスポートの詳細については、[を使用してアダプター](../core/using-adapters.md)を参照してください。                                                                |
|                                                                                                                                                        XLANGsBizTalkProperties.xsd                                                                                                                                                        |                                                                                                                                                        オーケストレーション エンジンは、このスキーマを使用します。                                                                                                                                                         |

## <a name="see-also"></a>参照  
 [BizTalk プロジェクト内の BizTalk 名前空間参照について](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)