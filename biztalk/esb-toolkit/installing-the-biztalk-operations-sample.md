---
title: BizTalk 操作サンプルをインストールする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4fa6aeb56c9d5e4ed65e80f0a43c2cdedcf8b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002579"
---
# <a name="installing-the-biztalk-operations-sample"></a>BizTalk 操作サンプルをインストールします。
Microsoft BizTalk 操作サンプルには、ESB BizTalk 操作のサービスをインストールして構成が必要です。 ESB BizTalk Operations サービスでは、インストールして、ESB 構成ツールを使用して構成するコア Web サービスの 1 つです。 詳細については、ESB 構成ツールを使用して、次を参照してください。 [ http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx)します。 BizTalk 操作 Web サービスの既定の場所は<http://localhost/ESB.BizTalkOperationsService/Operations.asmx>。 ただし、別の場所またはリモート サーバーでサービスをデプロイする場合、アプリケーション構成ファイルで変更することができます。  

 ソリューションのプロジェクトからの BizTalk 操作サンプルをインストールする必要があります。  

 **BizTalk 操作サンプルをインストールするには**  

1. インストールした \Source\Samples\BizTalkOperations フォルダーから ESB.BizTalkOperations.Test.Client.csproj という名前のソリューションを開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]に Visual Studio のサンプル。  

2. 使用して、**ビルド**] メニューの [ソリューションをコンパイルします。
