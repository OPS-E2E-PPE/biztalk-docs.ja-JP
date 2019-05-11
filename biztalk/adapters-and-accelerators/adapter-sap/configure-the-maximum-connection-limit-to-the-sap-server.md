---
title: SAP サーバーに最大接続数制限の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 858ed90e-b219-43cc-ad63-ae8e1eb2159a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4286fbbaeaca1aefaf6a7ea995a068eba25c0690
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373767"
---
# <a name="configure-the-maximum-connection-limit-to-the-sap-server"></a>SAP サーバーに最大接続数制限を構成します。
Data Provider for SAP では、プロバイダーによって内部的に開くことができる接続の最大数を制御するアダプターのクライアントが使用できます。 これは、CPIC_MAX_CONV、環境変数を設定して制御できます。  
  
 など CPIC_MAX_CONV が任意の数値に設定されている場合、いつでも開かれている RFC 接続の数はその数値に等しいまたはそれよりも小さいデータになります。  
  
> [!NOTE]
>  数値はこの値を設定するプロセスと appdomain で個別にすべてのサーバーに対して適用されます。  
  
 "X"プロセス レベルでの環境変数が設定であると、A と B の両方の接続の最大数、2 台のサーバーに接続する場合、アプリケーションでは、SAP のデータ プロバイダーを使用して、たとえば、A と B になります"x"それぞれします。