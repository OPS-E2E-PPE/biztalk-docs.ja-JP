---
title: バインド ファイルをカスタマイズする |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, binding files
- binding files
- binding files, about binding files
- binding files, customizing
ms.assetid: 4714e6c2-4912-43aa-ba5a-0be06916a30a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1534be96255084b963ed3883a1370af00f73b605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238370"
---
# <a name="customizing-binding-files"></a>バインド ファイルのカスタマイズ
バインド ファイルは、BizTalk 管理データベース内のアイテム、およびこれらのアイテム間のリレーションシップを記述する XML ファイルです。 バインド ファイルは、1 つの BizTalk 構成データベースから構成情報をエクスポートし、この情報を別の BizTalk 構成データベースにインポートする際に役立ちます。 たとえば、開発者は BizTalk ソリューションとその関連アイテムを開発環境でデザインし、これらのアイテムをバインド ファイルにエクスポートして、最後にこれらのアイテムを実稼動環境にインポートできます。 また、バインド ファイルを使用して、既存の構成を更新することもできます。 たとえば、開発環境内の構成の変更を、バインド ファイルを使用して実稼動環境に適用できます。 このトピックでは、既存の構成をバインド ファイルで更新する際の考慮事項、バインド ファイルの構造、およびバインド ファイルで設定できるアダプター固有の構成プロパティについて説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [バインド ファイルと共に、既存の構成を更新](../core/updating-an-existing-configuration-with-a-binding-file.md)  
  
-   [バインド ファイルの構造](../core/structure-of-a-binding-file.md)  
  
-   [統合 BizTalk アダプターの構成プロパティ](../core/configuration-properties-for-integrated-biztalk-adapters.md)