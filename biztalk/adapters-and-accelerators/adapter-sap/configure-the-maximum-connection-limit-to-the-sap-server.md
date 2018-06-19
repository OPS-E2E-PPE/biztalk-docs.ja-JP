---
title: SAP サーバーに最大接続数を構成する |Microsoft ドキュメント
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
ms.openlocfilehash: 853a3b78b82e242750e30099f847045ff590f125
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215850"
---
# <a name="configure-the-maximum-connection-limit-to-the-sap-server"></a>SAP サーバーに最大接続数を構成します。
Data Provider 用 SAP では、プロバイダーによって内部的に開くことのできる接続の最大数を制御するアダプターのクライアントを使用できます。 これは、CPIC_MAX_CONV、環境変数を設定して制御できます。  
  
 たとえば、CPIC_MAX_CONV が任意の数値に設定されている場合、いつでも開く RFC 接続の数はその数値に等しいまたはそれよりも少なくなります。  
  
> [!NOTE]
>  数値はすべてのサーバーにある個別のプロセス/アプリケーション ドメインがこの値の設定の適用になります。  
  
 "X"プロセス レベルでの環境変数が設定であると、A と B の両方の接続の最大数、2 台のサーバーに接続する場合、SAP 用データ プロバイダーを使用してアプリケーションをたとえば、A と B になります"x"それぞれします。