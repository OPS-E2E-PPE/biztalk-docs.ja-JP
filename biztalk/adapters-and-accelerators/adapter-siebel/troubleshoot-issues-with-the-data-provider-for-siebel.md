---
title: Data Provider for Siebel に関する問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, troubleshooting
- troubleshooting, Data Provider for Siebel
ms.assetid: 2bfe69a2-d6de-466d-9f36-f11c386c771c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adeae6cc42aebb1ddae3c3c3e769fdb77984d878
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370442"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-siebel"></a>Data Provider for Siebel に関する問題をトラブルシューティングします。
このセクションを使用する場合に発生する可能性のあるエラーを解決するトラブルシューティングの手法を使用して説明します、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。  
  
## <a name="known-issues"></a>既知の問題  
  
### <a name="data-provider-for-siebel-may-give-component-datareader-source-380-error"></a>Data Provider for Siebel「コンポーネント 'DataReader ソース' (380)」エラーを与える可能性があります。  
 **問題**  
  
 Siebel ビジネス コンポーネントで SELECT クエリを実行中に、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 「コンポーネント 'DataReader ソース' (380)」エラーを与える可能性があります。  
  
 **原因**  
  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]パラメーターの Siebel システムから受信した値は、パラメーターの maxLength プロパティを超えています。 このエラーを示します。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)