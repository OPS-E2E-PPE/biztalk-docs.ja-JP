---
title: WCF LOB Adapter SDK でサポートされているメッセージ交換パターンの表示 |Microsoft Docs
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
ms.openlocfilehash: eca67c0f5ebbb3220ebd6d1a836cc37f271df9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362649"
---
# <a name="view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK でサポートされているメッセージ交換パターンを表示します。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、基になるでサポートされているメッセージング パターンのいくつかの操作をサポートしている[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]要求/応答、一方向の通信など。 さまざまなトランスポートでは、異なるメッセージング パターンをサポートし、サポートされる対話の種類にも影響します。  
  
 次の表に示すパターンは、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  
  
|パターン|説明|  
|-------------|-----------------|  
|一方向受信|基幹業務システムから受信メッセージを受信するが、アダプターからの応答は発生しません。|  
|要求-応答受信|アダプターから適切な応答が必要ですが、基幹業務システムからは、受信メッセージを受信します。|  
|一方向送信|送信メッセージは、基幹業務システムに送信されますが、アダプターからの応答は発生しません。|  
|要求-応答の送信|送信メッセージは、応答がアダプターから予測を含む、基幹業務システムに送信されます。|  
|セッションの多い受信|受信メッセージは、一意のセッション内で基幹業務システムから受信されます。 アダプターから基幹業務システムでは、応答は発生しません。|  
|送信セッションの多い|送信メッセージは、一意のセッション内で、基幹業務システムに送信されます。 アダプターによって、基幹業務システムからの応答は発生しません。|  
  
 ターゲット アプリケーションの機能によってメッセージ パターンの選択をガイドします。  
  
## <a name="planning-for-sessions"></a>セッションの計画  
 メッセージング パターンでは、アダプターと基幹業務システム間で交換されるすべてのメッセージは、同じメッセージ交換の一部である必要があることを確認したいときにセッションを使用できます。 通常のセッションは、配信保証が必要ですが、メッセージ交換、アダプター開発者がいる可能性のあるその他の要件をサポートするためにも使用するときに使用されます。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]依存、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]のセッションをサポートします。 セッションの詳細については、次を参照してください。[セッション、インスタンス化、および同時実行](https://msdn.microsoft.com/library/ms731193.aspx)します。 
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)