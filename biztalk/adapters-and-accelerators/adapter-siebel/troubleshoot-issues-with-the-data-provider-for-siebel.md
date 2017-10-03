---
title: "Data Provider 用 Siebel に関する問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, troubleshooting
- troubleshooting, Data Provider for Siebel
ms.assetid: 2bfe69a2-d6de-466d-9f36-f11c386c771c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6e100635b1cb2db5c78ff713c8e6ad32d4e7d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-issues-with-the-data-provider-for-siebel"></a>Data Provider 用 Siebel に関する問題をトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性のあるエラーを解決するのには、トラブルシューティングの手法を使用して、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。  
  
## <a name="known-issues"></a>既知の問題  
  
### <a name="data-provider-for-siebel-may-give-component-datareader-source-380-error"></a>Data Provider 用 Siebel は「コンポーネント 'DataReader ソース' (380)」エラーになります  
 **問題**  
  
 Siebel ビジネス コンポーネントで SELECT クエリを実行中に、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 「コンポーネント 'DataReader ソース' (380)」エラーになります。  
  
 **原因**  
  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]パラメーターの Siebel システムから受信した値が、maxLength、パラメーターのプロパティを超えた場合、このエラーを示します。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)