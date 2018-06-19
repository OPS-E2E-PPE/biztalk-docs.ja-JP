---
title: WCF LOB Adapter SDK でサポートされているメッセージ交換のパターンを表示 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6662f17-b4f8-45fe-a22f-5d027dc9f2ff
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77fee95033e669bf584220461b330afbb9fd25b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225522"
---
# <a name="view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK でサポートされているメッセージ交換のパターンを表示します。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、基になるでサポートされるメッセージング パターンのいくつかの操作をサポートしている[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]要求/応答、一方向通信などです。 異なるトランスポートは、別のメッセージング パターンをサポートし、サポートされる対話の種類にも影響します。  
  
 次の表に示すパターンは、によって処理される、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
|パターン|Description|  
|-------------|-----------------|  
|一方向受信|基幹業務システムから受信された受信メッセージですがアダプターからの応答は発生しません。|  
|要求-応答受信|受信メッセージは、アダプターから適切な応答を待ち受けている基幹業務システムから受信されます。|  
|一方向送信|送信メッセージは、基幹業務システムに送信されますが、アダプターからの応答は発生しません。|  
|要求-応答の送信|送信メッセージは、アダプターから予測を応答と共に、基幹業務システムに送信されます。|  
|セッションの多い受信|受信メッセージは、一意のセッション内で、基幹業務システムから受信されます。 アダプターから基幹業務システムでは、応答は発生しません。|  
|送信セッションの多い|送信メッセージは、一意のセッション内で、基幹業務システムに送信されます。 アダプターによって、基幹業務システムからの応答は発生しません。|  
  
 対象アプリケーションの機能によってメッセージ パターンの選択をガイドします。  
  
## <a name="planning-for-sessions"></a>セッションの計画  
 メッセージング パターンは、アダプターおよび基幹業務システム間で交換されるすべてのメッセージは、同じメッセージ交換の一部である必要がありますを確認したいときにセッションを使用できます。 通常は、必要な配信保証がメッセージ交換、アダプター開発者可能性があるその他の要件をサポートするために使用することもできます、セッションは使用されます。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]依存、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]のセッションをサポートします。 セッションの詳細については、次を参照してください。[セッション、インスタンス化、および同時実行](https://msdn.microsoft.com/library/ms731193.aspx)です。 
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)