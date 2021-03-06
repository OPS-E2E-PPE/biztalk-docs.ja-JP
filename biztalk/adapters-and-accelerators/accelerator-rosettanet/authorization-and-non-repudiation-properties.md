---
title: 承認と否認不可プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authorization properties
- non-repudiation, properties
ms.assetid: e752b95b-9dae-4403-8f3e-3a0a50acd519
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d7088b25ec2526c19c60d21c9929afb92be42a7
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752762"
---
# <a name="authorization-and-non-repudiation-properties"></a>承認と否認不可プロパティ
このトピックでは、PIP (Partner Interface Process) の `Is Authorization Required`、`Non-Repudiation of Origin and Content`、および `Non-Repudiation Required (Acknowledgement of Receipt)` プロパティの動作について説明します。 これについても説明します、これらのプロパティの組み合わせを Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]をサポートしています。  

 これらのプロパティを設定して、**アクティビティ**のプロセス構成設定のセクションでは、プロセス構成プロパティのタブ、[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソール。 詳細については、[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)を参照してください。  

## <a name="property-behavior"></a>プロパティの動作  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、`Is Authorization Required`、`Non-Repudiation of Origin and Content`、および `Non-Repudiation Required (Acknowledgement of Receipt)` プロパティの設定に従って、次のように動作します。  


|                        プロパティ                         |                                                                                                                                                                             True の場合の動作                                                                                                                                                                             |                                                                               False の場合の動作                                                                               |
|---------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|               `Is Authorization Required`               | 受信アクションまたはシグナル メッセージが署名する必要があります。それ以外の場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]メッセージを拒否します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 個人またはロールが、アクティビティを実行する権限がない場合は、ビジネス ドキュメントは受け入れません。 | 着信アクション メッセージまたは着信シグナル メッセージが署名されている必要はありません。 メッセージの RNIF ヘッダー部分のパートナー DUNS 番号に単純な承認が適用されます。 |
|         `Non-Repudiation of Origin and Content`         |                                                                                                送信アクションまたはシグナル メッセージに署名されます。 アクション メッセージは、元の受信フォームで BTARNDATA データベースの MessageStorageOut テーブルに格納されます。                                                                                                 |                                                             送信アクションまたはシグナル メッセージは格納されません。                                                              |
| `Non-Repudiation Required (Acknowledgement of Receipt)` |                                                                                 着信アクション メッセージまたは着信シグナル メッセージが署名されている必要があります。 着信メッセージは、BTARNDATA データベースの MessageStorageIn テーブルに格納されます。 メッセージ ダイジェストが受信確認に含まれている必要があります。                                                                                  |                                                             着信アクション メッセージまたは着信シグナル メッセージは格納されません。                                                              |

## <a name="property-support"></a>プロパティのサポート  
 次の表に、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の `Is Authorization Required`、`Non-Repudiation of Origin and Content`、および `Non-Repudiation Required (Acknowledgement of Receipt)` プロパティの組み合わせのサポートを示します。  

> [!IMPORTANT]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 両方アクション メッセージとシグナル メッセージ、またはアクション メッセージでも 1 つのメッセージに署名するかする必要があります。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] アクションの署名がサインインしていない、サポートされていません信号をまたはその逆です。  
> 
> [!IMPORTANT]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が送信メッセージに署名した場合は、そのメッセージを BTARNArchive データベースの MessageStorageOut テーブルに保存する必要があります。  

|認証の必要性します。|[発信元とコンテンツの否認不可]|Non-Repudiation Required (Acknowledgement of Receipt)|BTARN によるサポートの有無|  
|-------------------------------|--------------------------------------------|--------------------------------------------------------------|-------------------------|  
|`False`|`False`|`False`|はい|  
|`False`|`False`|`True`|違います\*|  
|`False`|`True`|`False`|違います\*\*|  
|`False`|`True`|`True`|違います\*\*\*|  
|`True`|`False`|`False`|うん\*\*\*\*|  
|`True`|`False`|`True`|うん\*\*\*\*|  
|`True`|`True`|`False`|はい|  
|`True`|`True`|`True`|はい|  

 \* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] シグナルが署名して、アクションが署名されていないことを必要とするためには、この組み合わせをサポートしません。  

 \*\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] アクションに署名して、シグナルが署名されていないことを必要とするためには、この組み合わせをサポートしません。  

 \*\*\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 否認不可に設定するため、この組み合わせをサポートしません`True`アクションとシグナルの両方のことを意味[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]承認を実行します。 したがって、この組み合わせは有効ではありません。  

 \*\*\*\* 設定すると`Is Authorization Required`に`True`と`Non-Repudiation of Origin and Content`に`False`、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]メッセージを否認不可テーブルに保存します。  

## <a name="see-also"></a>参照  
 [プロセス構成を作成または編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)